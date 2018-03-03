---
title: "-Sdl (Aktivieren zusätzlicher Sicherheitsüberprüfungen) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
dev_langs:
- C++
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5cbcb74272fa7cae3dd0c641bd6371c8f0f9c204
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl (Aktivieren zusätzlicher Sicherheitsüberprüfungen)
Fügt empfohlene SDL-Prüfungen (Security Development Lifecycle) hinzu. Diese Prüfungen enthalten zusätzliche sicherheitsrelevante Warnungen als Fehler und zusätzliche sichere Codegenerierungsfunktionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/sdl[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ SDL** aktiviert eine Obermenge der grundlegenden sicherheitsüberprüfungen gebotenen [/GS](../../build/reference/gs-buffer-security-check.md) und überschreibt **/GS-**. Standardmäßig **/SDL** ist deaktiviert. **/SDL-** deaktiviert die zusätzlichen sicherheitsüberprüfungen.  
  
## <a name="compile-time-checks"></a>Überprüfungen zur Kompilierzeit  
 **/ SDL** ermöglicht diese Warnungen als Fehler behandelt werden:  
  
|Durch /sdl aktivierte Warnung|Entsprechender Befehlszeilenschalter|Beschreibung|  
|------------------------------|-------------------------------------|-----------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|Ein unärer Subtraktionsoperator wurde auf einen vorzeichenlosen Typ angewendet, was zu einem Ergebnis ohne Vorzeichen führte.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|Eine negative integrale Konstante wurde in einen vorzeichenlosen Typ konvertiert, was zu einem möglicherweise bedeutungslosen Ergebnis führte.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|Verwenden von `continue`, `break` oder `goto` Schlüsselwörter in einem `__finally` / `finally` Block verfügt über ein nicht definiertes Verhalten bei nicht ordnungsgemäßer Beendigung.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|Der Code, der eine Variable initialisiert, wird nicht ausgeführt.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|Verwendung einer nicht initialisierten lokalen Variablen.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|Verwendung einer möglicherweise nicht initialisierten lokalen Zeigervariablen.|  
|[C4789 GENERIERT](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|Pufferüberlauf, wenn bestimmte CRT-Funktionen (C Run-Time) verwendet werden.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Verwenden einer Funktion mit Pragma gekennzeichnete [veraltet](../../preprocessor/deprecated-c-cpp.md).|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|Verwenden einer Funktion als gekennzeichnet [veraltet](../../cpp/deprecated-cpp.md).|  
  
## <a name="runtime-checks"></a>Überprüfungen zur Laufzeit  
 Wenn **/SDL** ist aktiviert, generiert der Compiler Code zum Ausführen dieser Tests zur Laufzeit:  
  
-   Aktiviert den strict-Modus von **/GS** zur Laufzeit-pufferüberlauferkennung zur, entspricht dem Kompilieren mit `#pragma strict_gs_check(push, on)`.  
  
-   Führt eingeschränkte Zeigerbereinigung aus. In Ausdrücken ohne Dereferenzierungen und in Typen ohne benutzerdefinierten Destruktor werden Zeigerverweise nach einem Aufruf von `delete` auf eine ungültige Adresse festgelegt. Dies dient dazu, die Wiederverwendung von veralteten Zeigerverweisen zu verhindern.  
  
-   Führt Klassenmemberinitialisierung aus. Initialisiert bei der Objektinstanziierung (bevor der Konstruktor ausgeführt wird) automatisch alle Klassenmember auf null. Dies dient dazu, die Verwendung von nicht initialisierten Daten zu verhindern, die Klassenmembern zugeordnet sind, die der Konstruktor nicht explizit initialisiert.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Warnungen, / SDL und Verbessern der Erkennung von nicht initialisierten Variablen](http://go.microsoft.com/fwlink/p/?LinkId=331012).  
  
#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Auf der **allgemeine** Seite, wählen Sie die Option aus der **SDL-Prüfungen** Dropdown-Liste.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)