---
title: "EDITBIN-Optionen"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EDITBIN (Programm), Optionen"
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# EDITBIN-Optionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können EDITBIN verwenden, um Objektdateien, ausführbare Dateien und Dynamic Link Libraries \(DLLs\) zu ändern.  Optionen die Änderungen aufgeführt, die EDITBIN vornimmt.  
  
 Eine Option besteht aus einem Optionsbezeichner, entweder einem Bindestrich \(–\) oder einem Schrägstrich \(\/\), sowie dem darauf folgenden Optionsnamen.  Optionsnamen können nicht abgekürzt werden.  Einige Optionen haben Argumente, die nach einem Doppelpunkt angegeben sind \(: \).  Innerhalb einer Optionsangabe sind keine Leerzeichen oder Tabstopps zulässig.  Verwenden Sie eines oder mehrere Leerzeichen bzw. Tabstopps, um Optionsangaben in der Befehlszeile voneinander zu trennen.  Bei Optionsnamen und ihren Schlüsselwortargumente oder Dateinamen bestehenden Argumenten wird keine Groß\-\/Kleinschreibung berücksichtigt.  Beispielsweise \- Bindung und \/BIND haben die gleiche Bedeutung.  
  
 EDITBIN hat die folgenden Optionen:  
  
|Option|Zweck|  
|------------|-----------|  
|[\/ALLOWBIND](../../build/reference/allowbind.md)|Gibt an, ob eine DLL gebunden werden kann.|  
|[\/ALLOWISOLATION](../../build/reference/allowisolation.md)|Gibt Manifest Suchverhalten der DLL oder der ausführbaren Datei an.|  
|[\/APPCONTAINER](../../build/reference/appcontainer.md)|Gibt ob die App muss innerhalb Appcontainer – z. B. eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App ausgeführt werden.|  
|[\/BIND](../../build/reference/bind.md)|Legt die Adressen für die Einstiegspunkte in den angegebenen Objekten zur Geschwindigkeitsladezeit fest.|  
|[\/DYNAMICBASE](../../build/reference/dynamicbase.md)|Gibt an, ob die DLL oder ausführbare das Image bei Ladezeit zufällig zurückgesetzt werden können, indem sie Adressbereichslayoutzufallszuteilung \(ASLR\) verwenden.|  
|[\/ERRORREPORT](../../build/reference/errorreport-editbin-exe.md)|Gibt internen Fehlern Microsoft.|  
|[\/HEAP](../../build/reference/heap.md)|Legt die Größe des Heaps des ausführbaren Images in Bytes fest.|  
|[\/HIGHENTROPYVA](../../build/reference/highentropyva.md)|Gibt an, ob die DLL oder ausführbare das Image hohe Adressbereichs\-Layoutzufallszuteilung \(ASLR\) die Entropie \(64\-Bit\) unterstützt.|  
|[\/INTEGRITYCHECK](../../build/reference/integritycheck.md)|Gibt an, ob die digitale Signatur zur Ladezeit überprüft.|  
|[\/LARGEADDRESSAWARE](../../build/reference/largeaddressaware.md)|Gibt an, ob das Objekt Adressen unterstützt, die größer als zwei Gigabyte sind.|  
|[\/NOLOGO](../../build/reference/nologo-editbin.md)|Unterdrückt das EDITBIN\-Startbanner.|  
|[\/NXCOMPAT](../../build/reference/nxcompat.md)|Gibt an, ob das ausführbare Image mit Windows\-Datenausführungsverhinderung kompatibel ist.|  
|[\/REBASE](../../build/reference/rebase.md)|Legt Basisadressen die für die angegebenen Objekte fest.|  
|[\/RELEASE](../../build/reference/release.md)|Legt die Prüfsumme im Header fest.|  
|[\/SECTION](../../build/reference/section-editbin.md)|Überschreibt die Attribute eines Abschnitts.|  
|[\/STACK](../../build/reference/stack.md)|Legt die Größe des Stapels des ausführbaren Images in Bytes fest.|  
|[\/SUBSYSTEM](../../build/reference/subsystem.md)|Gibt der Ausführungsumgebung an.|  
|[\/SWAPRUN](../../build/reference/swaprun.md)|Gibt an, dass, das ausführbare Image zur Seitendatei kopiert werden muss, und anschließend von dort ausgeführt.|  
|[\/TSAWARE](../../build/reference/tsaware.md)|Gibt an, dass die App entworfen wird, um in einer Umgebung ausgeführt mit mehreren Benutzern.|  
|[\/VERSION](../../build/reference/version.md)|Legt die Versionsnummer im Header fest.|  
  
## Siehe auch  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)   
 [EDITBIN\-Referenz](../../build/reference/editbin-reference.md)