---
title: Linkertoolfehler Lnk1123 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1123
dev_langs: C++
helpviewer_keywords: LNK1123
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ade68d51125167c34fc46f23a7c9ce7eccfdef5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1123"></a>Linkertoolfehler LNK1123
Fehler bei der Konvertierung in COFF: Datei ist ungültig oder beschädigt  
  
 Eingabedateien müssen das Common Object File Format(COFF)-Format haben. Besitzt eine Eingabedatei kein COFF-Format, versucht der Linker automatisch, 32-Bit-OMF-Objekte in COFF zu konvertieren, oder führt CVTRES.EXE aus, um Ressourcendateien zu konvertieren. Diese Meldung gibt an, dass der Linker die Datei nicht konvertieren konnte. Das kann auch bei der Verwendung einer inkompatiblen Version von CVTRES.EXE aus einer anderen Installation von Visual Studio, dem Windows Development Kit oder .NET Framework auftreten.  
  
> [!NOTE]
>  Wenn Sie eine frühere Version von Visual Studio ausführen, wird die automatische Konvertierung möglicherweise nicht unterstützt.  
  
### <a name="to-fix-the-problem"></a>So beheben Sie dieses Problem  
  
-   Übernehmen Sie alle Servicepacks und Updates für Ihre Version von Visual Studio. Dies ist besonders wichtig für Visual Studio 2010.  
  
-   Versuchen Sie das Erstellen mit deaktivierten inkrementellen Verknüpfen. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. In der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften**, **Linker**. Ändern Sie den Wert der **inkrementelles Verknüpfen aktivieren** auf **keine**.  
  
-   Überprüfen Sie, ob die Version von CVTRES.EXE, die zuerst in Ihrer PATH-Umgebungsvariable gefunden wird, der Version der in Ihrem Projekt verwendeten Buildtoos oder der Version des Plattformtoolsets entspricht.  
  
-   Versuchen Sie, die Option „Manifest einbetten“ zu deaktivieren. Wählen Sie in der Menüleiste **Projekt** und **Eigenschaften** aus. In der **Eigenschaftenseiten** Dialogfeld erweitern Sie **Konfigurationseigenschaften**, **Manifesttool**, **ein- und Ausgabe**. Ändern Sie den Wert der **Manifest einbetten** auf **keine**.  
  
-   Stellen Sie sicher, dass der Dateityp gültig ist. Stellen Sie zum Beispiel sicher, dass ein OMF-Objekt ein 32-Bit-Objekt und kein 16-Bit-Objekt ist. Weitere Informationen finden Sie unter [. OBJ-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md) und [Microsoft PE- und COFF-Spezifikation](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Stellen Sie sicher, dass die Datei nicht beschädigt ist. Erstellen Sie neu, falls erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [. OBJ-Dateien als Linkereingabe](../../build/reference/dot-obj-files-as-linker-input.md)   
 [EDITBIN-Referenz](../../build/reference/editbin-reference.md)   
 [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md)