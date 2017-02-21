---
title: "/ENTRY (Symbol f&#252;r Einstiegspunkt) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/entry"
  - "VC.Project.VCLinkerTool.EntryPointSymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ENTRY (Linkeroption)"
  - "ENTRY (Linkeroption)"
  - "-ENTRY (Linkeroption)"
  - "Startadresse"
ms.assetid: 26c62ba2-4f52-4882-a7bd-7046a0abf445
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /ENTRY (Symbol f&#252;r Einstiegspunkt)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ENTRY:function  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *Funktion*  
 eine Funktion, die eine benutzerdefinierte Startadresse für eine EXE\-Datei oder eine DLL festlegt.  
  
## Hinweise  
 Die \/ENTRY\-Option gibt eine Einstiegspunktfunktion als Startadresse für eine EXE\-Datei oder DLL an.  
  
 Die Funktion muss mit der Aufrufkonvention `__stdcall` definiert worden sein.  Die Parameter und der Rückgabewert hängen davon ab, ob das Programm eine Konsolenanwendung, eine Windows\-Anwendung oder eine DLL\-Datei ist.  Es wird empfohlen, dass Sie es dem Linker überlassen, den Einstiegspunkt festzulegen, damit die C\-Laufzeitbibliothek fehlerfrei initialisiert wird und C\+\+\-Konstruktoren für statische Objekte ausgeführt werden.  
  
 Standardmäßig ist die Startadresse ein Funktionsname aus der C\-Laufzeitbibliothek.  Der Linker wählt sie, wie in der folgenden Tabelle angegeben, entsprechend den Programmattributen aus.  
  
|Funktionsname|Standardeinstellung für|  
|-------------------|-----------------------------|  
|**mainCRTStartup** \(oder **wmainCRTStartup**\)|Eine Anwendung, die **\/SUBSYSTEM:CONSOLE** verwendet; ruft **main** \(oder **wmain**\) auf|  
|**WinMainCRTStartup** \(oder **wWinMainCRTStartup**\)|Eine Anwendung, die **\/SUBSYSTEM:WINDOWS** verwendet; ruft `WinMain` \(oder **wWinMain**\) auf, was mit `__stdcall` definiert wird|  
|**\_DllMainCRTStartup**|Eine DLL; ruft `DllMain` auf, was mit `__stdcall` definiert wird, falls vorhanden|  
  
 Wenn die Option [\/DLL](../../build/reference/dll-build-a-dll.md) oder [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) nicht angegeben wird, wählt der Linker ein Subsystem und einen Einstiegspunkt aus, je nachdem, ob **main** oder `WinMain` definiert ist.  
  
 Die Funktionen **main**, `WinMain` und `DllMain` sind die drei Formen des benutzerdefinierten Einstiegspunkts.  
  
 Beim Erstellen eines verwalteten Bildes muss die mit \/ENTRY angegebene Funktion über die Signatur \(LPVOID *var1*, DWORD *var2*, LPVOID *var3*\) verfügen.  
  
 Informationen darüber, wie Sie einen eigenen DllMain\-Einstiegspunkt definieren, finden Sie unter [Verhalten der Laufzeitbibliothek](../../build/run-time-library-behavior.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Erweitert**.  
  
4.  Ändern Sie die Eigenschaft **Einstiegspunkt**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EntryPointSymbol*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)