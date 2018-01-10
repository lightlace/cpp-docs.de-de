---
title: "Ausgabe (Gerätekontext) Klassen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.output
dev_langs: C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db7080c263ee6e98d458381d59446263490dfd7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="output-device-context-classes"></a>Klassen für die Ausgabe (Gerätekontext)
Diese Klassen kapseln die verschiedenen Typen von Gerätekontexte, die in Windows verfügbar.  
  
 Die meisten der folgenden Klassen kapseln ein Handle für einen Gerätekontext für Windows. Ein Gerätekontext ist ein Windows-Objekt, das Informationen zu den zeichnen Attributen von einem Gerät wie einer Bildschirmanzeige oder einen Drucker enthält. Alle zeichnen-Aufrufe erfolgen über einen Gerätekontext Objekt. Zusätzliche Klassen abgeleitet `CDC` spezielle Gerätekontext Funktionen, einschließlich der Unterstützung für Windows-Metadateien kapseln.  
  
 [CDC](../mfc/reference/cdc-class.md)  
 Die Basisklasse für Gerätekontexte. Direkt für den Zugriff auf die gesamte Anzeige und für den Zugriff auf Nondisplay Kontexten wie z. B. Drucker verwendet.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 Einen Anzeigekontext verwendet `OnPaint` Memberfunktionen von Windows. Ruft automatisch `BeginPaint` auf Konstruktion und `EndPaint` Zerstörung.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Einen Anzeigekontext für Clientbereiche von Windows. Verwendet, z. B. eine sofortige Reaktion auf Mausereignisse gezeichnet werden soll.  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 Einen Anzeigekontext für gesamte Windows, einschließlich sowohl Client als auch nicht-Bereiche.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Einen Gerätekontext für Windows-Metadateien. Eine Windows-Metadatei enthält eine Sequenz von Graphics Device Interface (GDI)-Befehlen an, die zum Erstellen eines Images wiedergegeben werden kann. Aufrufe an die Memberfunktionen von einem `CMetaFileDC` werden in einer Metadatei aufgezeichnet.  
  
## <a name="related-classes"></a>Verwandte Klassen  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Koordinate (X, y)-Paare enthält.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Enthält Abstand, relativen Positionen oder paarweise zugeordneten Werte.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Enthält die Koordinaten der rechteckige Bereiche.  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 Kapselt einen GDI-Bereich zum Bearbeiten von einen elliptischen, polygonale oder unregelmäßige Bereich innerhalb eines Fensters. Zusammen mit den Clipping-Memberfunktionen in der Klasse verwendet `CDC`.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Zeigt an, und die Benutzeroberfläche für das Ändern der Größe und Verschieben von rechteckigen Objekten behandelt.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Stellt ein Standarddialogfeld für eine Farbe auswählen.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Stellt ein Standarddialogfeld zum Auswählen einer Schriftart an.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Stellt ein Standarddialogfeld zum Drucken einer Datei an.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

