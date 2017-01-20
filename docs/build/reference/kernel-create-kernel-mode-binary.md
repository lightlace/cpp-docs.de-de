---
title: "/kernel (Binary f&#252;r den Kernelmodus erstellen)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "/kernel"
  - "/kernel-"
dev_langs: 
  - "C++"
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# /kernel (Binary f&#252;r den Kernelmodus erstellen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Binärdatei erstellt, die im Kernel von Windows ausgeführt werden kann.  
  
## Syntax  
  
```  
/kernel[-]  
```  
  
## Argumente  
 **\/kernel**  
 Der Code im aktuellen Projekt wurde kompiliert und verknüpft mithilfe eines Satzes C\+\+\-Sprachregeln, die spezifisch sind, die codiert werden, wird im Kernelmodus.  
  
 **\/kernel\-**  
 Der Code im aktuellen Projekt wurde kompiliert und verknüpft, ohne die C\+\+\-Sprachregeln verwenden, die spezifisch sind, die zu Codefehlern, durchläuft in Kernelmodus\-.  
  
## Hinweise  
 Es gibt keine `#pragma`\-Entsprechung, zum Steuern dieser Option.  
  
 Der **\/kernel**, der angibt Option weist den Compiler und Linker mit, um zu übergeben, die Sprachfunktionen im Kernelmodus und sicherzustellen zulässig sind ob die Sie genügend Ausdruckskraft haben, Ablaufinstabilität zu vermeiden, die in Kernelmodus\- C\+\+ eindeutig ist.  Dies wird erzielt, indem die Verwendung von C\+\+ verhindert, abgeschlossen, die im Kernelmodus störend sind und mit Warnungen für C\+\+ bereitstellen, die möglicherweise Auswirkungen sind, sondern, kann nicht deaktiviert werden.  
  
 Die **\/kernel** \- Option gilt die Compiler\- und Linkerphasen eines Builds zu und ist auf Projektebene festgelegt.  Führen Sie den Schalter **\/kernel**, um dem Compiler anzugeben, die sich ergebende Binärdatei, nachdem der verknüpft hat, in den Kernel von Windows geladen werden soll.  Der Compiler schränkt das Spektrum von C\+\+ auf eine Teilmenge ein, die dem Kernel kompatibel ist.  
  
 Die folgende Tabelle zeigt Änderungen im Compilerverhalten auf, wenn **\/kernel** angegeben wird.  
  
|Verhaltens\-Typ|Verhalten **\/kernel**|  
|---------------------|----------------------------|  
|C\+\+\-Ausnahmebehandlung|Deaktiviert.  Alle Instanzen der Schlüsselwörter `throw` und `try` geben einen Compilerfehler aus \(außer der Ausnahmespezifikation `throw()`\).  Keine **\/EH** Optionen sind mit **\/kernel**, außer **\/EH\-** kompatibel.|  
|RTTI|Deaktiviert.  Alle Instanzen der Schlüsselwörter `dynamic_cast` und `typeid` geben einen Compilerfehler aus, es sei denn, `dynamic_cast` statisch verwendet wird.|  
|`new` und `delete`|Sie müssen den `new()` oder `delete()` explizit definieren; Operator weder stellen der Compiler noch die Laufzeit eine Standarddefinition.|  
  
 Benutzerdefinierte Aufrufkonventionen, die [\/GS](../../build/reference/gs-buffer-security-check.md) Buildoption und alle Optimierungen sind zulässig, wenn Sie die Option **\/kernel** verwenden.  Das Inlining wird größtenteils von **\/kernel** nicht beeinflusst, wenn dieselbe Semantik vom Compiler berücksichtigt ist.  Wenn Sie überprüfen möchten, ob der `__forceinline` Inliningqualifizierer berücksichtigt wird, müssen Sie dass die Warnung von [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) Überprüfen, aktiviert ist, sodass Sie wissen, wann eine Einzelheits `__forceinline`\-Funktion ist nicht inline ist.  
  
 Wenn dem Compiler der Schalter **\/kernel** übergeben wird, definiert ein Präprozessormakro vor, das `_KERNEL_MODE` genannt und den Wert **1** hat.  Sie können dieses verwenden, um Code bedingt auf Grundlage zu kompilieren, ob die Ausführungsumgebung im Benutzermodus oder im Kernelmodus ist.  Im folgenden Code werden beispielsweise an, dass die Klasse in einem residenten Arbeitsspeichersegment sein sollte, wenn sie für Kernelmodusausführung kompiliert wird.  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
  
};  
  
```  
  
 Einige folgende Kombinationen der Zielarchitektur und der **\/arch** \- Option erzeugt einen Fehler, wenn sie mit **\/kernel** verwendet werden:  
  
-   **\/arch:{SSE&#124;SSE2&#124;AVX}** sind für x86 unterstützt.  Nur **\/arch:IA32** wird mit **\/kernel** auf x86 unterstützt.  
  
-   **\/arch:AVX** wird nicht mit **\/kernel** auf x64 unterstützt.  
  
 Beim Erstellen mit **\/kernel** führt auch **\/kernel** an den Linker.  Hers, wie dieses Linkerverhalten betroffen:  
  
-   Inkrementelles Verknüpfen wird deaktiviert.  Wenn Sie der Befehlszeile **\/incremental** hinzufügen, generiert der Linker diesem schwer wiegender Fehler:  
  
     **LINK : fatal error LNK1295: '\/INCREMENTAL' not compatible with '\/KERNEL' specification; link without '\/INCREMENTAL'**  
  
-   Der Linker untersucht jede Objektdatei \(oder einen Archivmember enthaltenden aus den statischen Bibliotheken\) um festzustellen, ob er kompiliert werden kann, indem die **\/kernel** \- Option verwendet, war jedoch nicht.  Wenn eine " $HOME\/teamexplorer Instanzen erfüllen dieses Kriterium, die Links des Linkers weiterhin erfolgreich jedoch eine Warnung, wie in der folgenden Tabelle gezeigt.  
  
    ||**\/kernel**\-Objekt|**\/kernel\-**, MASM\-obj obj oder cvtresed|Kombination von **\/kernel** und **\/kernel\-** objs|  
    |-|--------------------------|-------------------------------------------------|----------------------------------------------------------|  
    |**Link \/kernel**|ja|ja|Ja mit dem von LNK4257 Warnung|  
    |**link**|ja|ja|ja|  
  
     **LNK4257 linking object not compiled with \/KERNEL ; image may not run**  
  
 Die **\/kernel** \- Option und die Option **\/driver** werden unabhängig und auch nicht beeinflusst der andere.  
  
### So die Compileroption \/kernel\- in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Im Feld **Zusätzliche Optionen** fügen Sie `/kernel` oder `/kernel-` hinzu.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)