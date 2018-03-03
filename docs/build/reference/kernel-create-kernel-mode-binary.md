---
title: "-Kernel (Kernel erstellen Modus binär) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /kernel
- /kernel-
dev_langs:
- C++
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0e20df59788577acb680cbd18b737f7ec2d7822
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel (Binary für den Kernelmodus erstellen)
Erstellt eine Binärdatei, die im Kernel von Windows ausgeführt werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
/kernel[-]  
```  
  
## <a name="arguments"></a>Argumente  
 **/ Kernel für den**  
 Der Code im aktuellen Projekt wird kompiliert und verknüpft werden anhand eines Satzes von Regeln der C++-Sprache, die auf Code beziehen, die im Kernel-Modus ausgeführt wird.  
  
 **/Kernel-**  
 Der Code im aktuellen Projekt wird kompiliert und verknüpft werden, ohne die Regeln der C++-Sprache, die auf Code beziehen, die im Kernel-Modus ausgeführt wird.  
  
## <a name="remarks"></a>Hinweise  
 Es gibt keine `#pragma`-Entsprechung, zum Steuern dieser Option.  
  
 Angeben der **/Kernel für den** Option weist den Compiler und Linker zu vermitteln, welche Funktionen der Programmiersprache im Kernelmodus zulässig sind, und um sicherzustellen, dass, die Sie über ausreichende Ausdrucksstärke Runtime Instabilität zu vermeiden, die für den Kernelmodus C++ eindeutig. Dies wird erreicht, indem verbietet die Verwendung von C++-Sprachfunktionen, die unterbrechen den Betrieb im Kernel-Modus und Warnungen für C++-Sprachfunktionen, die potenziell unterbrechen den Betrieb, aber nicht deaktiviert werden.  
  
 Die **/Kernel für den** Option gilt für Compiler und Linker Phasen eines Builds und auf Projektebene festgelegt ist. Übergeben Sie die **/Kernel für den** Switch für den Compiler an, dass die resultierende Binärdatei nach dem verknüpfen, in der Windows-Kernel geladen werden soll. Der Compiler wird das Spektrum von C++-Sprachfunktionen, um eine Teilmenge einzugrenzen, die mit dem Kernel kompatibel ist.  
  
 Die folgende Tabelle enthält die Änderungen im Compilerverhalten beim **/Kernel für den** angegeben ist.  
  
|Verhaltenstyp|**/ Kernel für den** Verhalten|  
|-------------------|---------------------------|  
|C++-Ausnahmebehandlung|Deaktiviert. Alle Instanzen der `throw` und `try` Schlüsselwörter ausgeben ein Compilerfehler ausgelöst (mit Ausnahme der Ausnahmespezifikation `throw()`). Nicht **/EH** Optionen sind kompatibel mit **/Kernel für den**, mit Ausnahme von **/EH-**.|  
|RTTI|Deaktiviert. Alle Instanzen der `dynamic_cast` und `typeid` Schlüsselwörter einen Compilerfehler ausgeben, es sei denn, `dynamic_cast` statisch verwendet wird.|  
|`new` und `delete`|Sie müssen explizit definieren, die `new()` oder `delete()` Operator; weder der Compiler noch die Common Language Runtime eine Default-Definition bereitstellt.|  
  
 Benutzerdefinierte Aufrufkonventionen, die [/GS](../../build/reference/gs-buffer-security-check.md) "Release" und alle Optimierungen sind zulässig, bei der Verwendung der **/Kernel für den** Option. Inlining größtenteils nicht betroffen ist **/Kernel für den**, mit der gleichen Semantik, die vom Compiler berücksichtigt. Wenn Sie sicherstellen, dass möchten die `__forceinline` inlining Qualifizierer wird berücksichtigt, stellen Sie sicher, dass die Warnung [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) wird aktiviert, damit Sie wissen, wenn ein bestimmter `__forceinline` Funktion ist nicht inline.  
  
 Wenn Sie der Compiler übergeben der **/Kernel für den** Switch, sind ein Präprozessormakro mit dem Namen vordefiniert `_KERNEL_MODE` und hat den Wert **1**. Sie können dies um basierend darauf, ob die ausführungsumgebung im Benutzermodus oder Kernelmodus Code bedingt zu kompilieren. Der folgende Code gibt beispielsweise, dass die Klasse in einem Speichersegment nicht auslagerbaren werden soll, sofern dies für den Kernelmodus kompiliert wird.  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
   // ...
};  
```  
  
 Einige der folgenden Kombinationen von der Zielarchitektur und **/arch** Option löst einen Fehler aus, wenn bei Verwendung **/Kernel für den**:  
  
-   **/ arch: {SSE &#124; SSE2 &#124; AVX}** X86 werden nicht unterstützt. Nur **/arch:IA32** wird unterstützt, wobei **/Kernel für den** auf X86.  
  
-   **/ arch: AVX** wird nicht unterstützt, mit **/Kernel für den** auf X64.  
  
 Beim Erstellen mit **/Kernel für den** übergibt auch **/Kernel für den** an den Linker. Anna ist, wie dies wirkt sich Linker Verhalten auf:  
  
-   Inkrementelles Verknüpfen deaktiviert ist. Wenn Sie hinzufügen **/ incremental** an die Befehlszeile der Linker diese schwerwiegenden Fehler ausgibt:  
  
     **LINK: Schwerwiegender Fehler LNK1295: "/ INCREMENTAL" nicht kompatibel mit "/ KERNEL" Spezifikation; Verknüpfen Sie ohne "/ INCREMENTAL"**  
  
-   Der Linker überprüft jede Objektdatei (oder ein enthalten Archiv-Member von statischen Bibliotheken), um festzustellen, ob mit kompiliert wurden konnte die **/Kernel für den** Option wurde jedoch nicht. Alle Instanzen dieses Kriterium erfüllt, wird der Linker weiterhin erfolgreich verknüpft, aber möglicherweise eine Warnung ausgeben, wie in der folgenden Tabelle gezeigt.  
  
    ||**/ Kernel für den** Obj|**/Kernel-** Obj MASM-Obj oder Cvtresed|Mischen von **/Kernel für den** und **/kernel-** Objs|  
    |-|----------------------|-----------------------------------------------|-------------------------------------------------|  
    |**/ Link Kernel für den**|Ja|Ja|Ja, mit der Warnung LNK4257|  
    |**Link**|Ja|Ja|Ja|  
  
     **LNK4257 Verknüpfungsobjekt mit/Kernel für den nicht kompiliert; Abbild kann möglicherweise nicht ausgeführt.**  
  
 Die **/Kernel für den** Option und die **/Driver** Option unabhängig voneinander betrieben und weder wirkt sich auf die andere.  
  
### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>So legen Sie die Compileroption/Kernel für den in Visual Studio fest  
  
1.  Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  In der **Zusatzoptionen** fügen `/kernel` oder `/kernel-`.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)