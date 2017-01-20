---
title: "/sdl (Aktivieren zus&#228;tzlicher Sicherheits&#252;berpr&#252;fungen)"
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
  - "VC.Project.VCCLCompilerTool.SDLCheck"
dev_langs: 
  - "C++"
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# /sdl (Aktivieren zus&#228;tzlicher Sicherheits&#252;berpr&#252;fungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügt empfohlene SDL\-Prüfungen \(Security Development Lifecycle\) hinzu.  Diese Prüfungen enthalten zusätzliche sicherheitsrelevante Warnungen als Fehler und zusätzliche sichere Codegenerierungsfunktionen.  
  
## Syntax  
  
```  
/sdl[-]  
```  
  
## Hinweise  
 **\/sdl** aktiviert eine Obermenge der grundlegenden Sicherheitsüberprüfungen, die von [\/GS](../../build/reference/gs-buffer-security-check.md) bereitgestellt werden, und überschreibt **\/GS\-**.  **\/sdl** ist standardmäßig deaktiviert.  **\/sdl\-** deaktiviert die zusätzlichen Sicherheitsüberprüfungen.  
  
## Überprüfungen zur Kompilierzeit  
 **\/sdl** aktiviert die folgenden Warnungen als Fehler:  
  
|Durch \/sdl aktivierte Warnung|Entsprechender Befehlszeilenschalter|Beschreibung|  
|------------------------------------|------------------------------------------|------------------|  
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|\/we4146|Ein unärer Subtraktionsoperator wurde auf einen vorzeichenlosen Typ angewendet, was zu einem Ergebnis ohne Vorzeichen führte.|  
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|\/we4308|Eine negative integrale Konstante wurde in einen vorzeichenlosen Typ konvertiert, was zu einem möglicherweise bedeutungslosen Ergebnis führte.|  
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|\/we4532|Die Verwendung der Schlüsselwörter `continue`, `break` oder `goto` in einem `__finally`\/`finally`\-Block führt bei nicht ordnungsgemäßer Beendigung zu undefiniertem Verhalten.|  
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|\/we4533|Der Code, der eine Variable initialisiert, wird nicht ausgeführt.|  
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|\/we4700|Verwendung einer nicht initialisierten lokalen Variablen.|  
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|\/we4703|Verwendung einer möglicherweise nicht initialisierten lokalen Zeigervariablen.|  
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|\/we4789|Pufferüberlauf, wenn bestimmte CRT\-Funktionen \(C Run\-Time\) verwendet werden.|  
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|\/we4995|Verwendung einer mit dem Pragma [deprecated](../../preprocessor/deprecated-c-cpp.md) gekennzeichneten Funktion.|  
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|\/we4996|Verwendung einer als [deprecated](../../cpp/deprecated-cpp.md) markierten Funktion.|  
  
## Überprüfungen zur Laufzeit  
 Wenn **\/sdl** aktiviert ist, generiert der Compiler Code, um die folgenden Überprüfungen zur Laufzeit ausführen:  
  
-   Aktiviert den Strict\-Modus der **\/GS**\-Pufferüberlauferkennung zur Laufzeit; entspricht dem Kompilieren mit `#pragma strict_gs_check(push, on)`.  
  
-   Führt eingeschränkte Zeigerbereinigung aus.  In Ausdrücken ohne Dereferenzierungen und in Typen ohne benutzerdefinierten Destruktor werden Zeigerverweise nach einem Aufruf von `delete` auf eine ungültige Adresse festgelegt.  Dies dient dazu, die Wiederverwendung von veralteten Zeigerverweisen zu verhindern.  
  
-   Führt Klassenmemberinitialisierung aus.  Initialisiert bei der Objektinstanziierung \(bevor der Konstruktor ausgeführt wird\) automatisch alle Klassenmember auf null.  Dies dient dazu, die Verwendung von nicht initialisierten Daten zu verhindern, die Klassenmembern zugeordnet sind, die der Konstruktor nicht explizit initialisiert.  
  
## Hinweise  
 Weitere Informationen finden Sie im Thema über [Warnungen, \/sdl und Verbessern der Erkennung von nicht initialisierten Variablen](http://go.microsoft.com/fwlink/p/?LinkId=331012).  
  
#### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Auf der Seite **Allgemein** wählen Sie die Option aus der Dropdownliste **SDL\-Prüfungen** aus.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)