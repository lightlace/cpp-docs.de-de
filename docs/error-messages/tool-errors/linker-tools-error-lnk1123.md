---
title: "Linkertoolfehler LNK1123"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1123"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1123"
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK1123
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler bei der Konvertierung in COFF: Datei ist ungültig oder beschädigt  
  
 Eingabedateien müssen das Common Object File Format\(COFF\)\-Format haben.  Besitzt eine Eingabedatei kein COFF\-Format, versucht der Linker automatisch, 32\-Bit\-OMF\-Objekte in COFF zu konvertieren, oder führt CVTRES.EXE aus, um Ressourcendateien zu konvertieren.  Diese Meldung gibt an, dass der Linker die Datei nicht konvertieren konnte.  Das kann auch bei der Verwendung einer inkompatiblen Version von CVTRES.EXE aus einer anderen Installation von Visual Studio, dem Windows Development Kit oder .NET Framework auftreten.  
  
> [!NOTE]
>  Wenn Sie eine frühere Version von Visual Studio ausführen, wird die automatische Konvertierung möglicherweise nicht unterstützt.  
  
### So beheben Sie dieses Problem  
  
-   Übernehmen Sie alle Servicepacks und Updates für Ihre Version von Visual Studio.  Dies ist besonders wichtig für Visual Studio 2010.  
  
-   Versuchen Sie das Erstellen mit deaktivierten inkrementellen Verknüpfen.  Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus.  Erweitern Sie im Dialogfeld **Eigenschaftenseiten** unter **Konfigurationseigenschaften** die Kategorie **Linker** aus.  Ändern Sie den Wert von **inkrementelles Verknüpfen** aktivieren auf **Nein**.  
  
-   Überprüfen Sie, ob die Version von CVTRES.EXE, die zuerst in Ihrer PATH\-Umgebungsvariable gefunden wird, der Version der in Ihrem Projekt verwendeten Buildtoos oder der Version des Plattformtoolsets entspricht.  
  
-   Versuchen Sie, die Option „Manifest einbetten“ zu deaktivieren.  Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus.  Erweitern Sie im Dialogfeld **Eigenschaftenseiten** Folgendes: **Konfigurationseigenschaften**, **Manifesttool**, **Eingabe und Ausgabe**.  Ändern Sie den Wert von **Manifest einbetten** in **Nein**.  
  
-   Stellen Sie sicher, dass der Dateityp gültig ist.  Stellen Sie zum Beispiel sicher, dass ein OMF\-Objekt ein 32\-Bit\-Objekt und kein 16\-Bit\-Objekt ist.  Weitere Informationen finden Sie unter [.OBJ\-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md) und [Microsoft PE\- und COFF\-Spezifikation](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Stellen Sie sicher, dass die Datei nicht beschädigt ist.  Erstellen Sie neu, falls erforderlich.  
  
## Siehe auch  
 [.OBJ\-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md)   
 [EDITBIN\-Referenz](../../build/reference/editbin-reference.md)   
 [DUMPBIN\-Referenz](../../build/reference/dumpbin-reference.md)