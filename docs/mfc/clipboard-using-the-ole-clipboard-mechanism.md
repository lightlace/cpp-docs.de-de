---
title: 'Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [OLE], Clipboard
- OLE Clipboard
- Clipboard [MFC], OLE formats
- OLE Clipboard, formats
- formats [MFC], Clipboard for OLE
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4940c614046e3ca407887e05e84c811a156d9c3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342536"
---
# <a name="clipboard-using-the-ole-clipboard-mechanism"></a>Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus
OLE verwendet Standardformate und einige OLE-spezifische Formate zum Übertragen von Daten über die Zwischenablage.  
  
 Wenn Sie Ausschneiden oder Kopieren von Daten aus einer Anwendung, ist die Daten in die Zwischenablage, die weiter unten in der Einfügevorgänge verwendet werden gespeichert. Diese Daten sind in verschiedenen Formaten. Wenn ein Benutzer wählt Daten aus der Zwischenablage einfügen, kann die Anwendung die folgenden Formate verwenden auswählen. Wählen Sie das Format, das meisten Informationen bereitstellt, es sei denn, der speziell für ein bestimmtes Format Frage mit Inhalte einfügen, sollte die Anwendung geschrieben werden. Bevor Sie fortfahren, sollten Sie zum Lesen der [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Themen. Beschreiben sie die Grundlagen, wie von Datenübertragungen und wie sie in Ihren Anwendungen implementieren.  
  
 Windows definiert eine Reihe von Standardformaten, die zum Übertragen von Daten über die Zwischenablage verwendet werden können. Dazu gehören Metadateien, Text und Bitmaps. OLE definiert eine Reihe von OLE-spezifische Formate sowie. Für Anwendungen, die mehr Details als durch diese Standardformate angegebenen benötigen, ist es ratsam, ihre eigenen benutzerdefinierten Zwischenablageformate registrieren. Verwenden Sie die Win32-API-Funktion [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) dazu.  
  
 Microsoft Excel registriert z. B. ein benutzerdefiniertes Format für Tabellen. Dieses Format enthält wesentlich mehr Informationen als z. B., eine Bitmap. Wenn diese Daten in eine Anwendung, die das Arbeitsblattformat unterstützt eingefügt werden, werden alle Formeln und Werte aus dem Arbeitsblatt werden beibehalten und können bei Bedarf aktualisiert werden. Microsoft Excel wird auch Daten in der Zwischenablage in Formaten, damit sie als OLE-Element eingefügt werden können. Alle OLE-Document-Container kann diese Informationen als eingebettetes Element einfügen. Diese eingebettete-Element kann mit Microsoft Excel geändert werden. Die Zwischenablage enthält auch eine einfache Bitmap des Bilds des ausgewählten Datumsbereichs in der Kalkulationstabelle. Dies kann auch in OLE Document-Container oder einer Bitmap-Editoren wie Paint eingefügt werden. Im Fall einer Bitmap besteht jedoch keine Möglichkeit, die Daten als ein Arbeitsblatt bearbeiten können.  
  
 Um die maximale Menge an Informationen aus der Zwischenablage abgerufen werden, müssen Anwendungen für diese benutzerdefinierte Formate Auschecken, bevor Sie Daten aus der Zwischenablage einfügen.  
  
 Z. B., um den Befehl "Ausschneiden" zu aktivieren, können Sie einem Handler etwa wie folgt schreiben:  
  
 [!code-cpp[NVC_MFCListView#3](../atl/reference/codesnippet/cpp/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [Verwenden der Windows-Zwischenablage](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [OLE-Objekte und Daten Datenquellen und uniform Data transfer](../mfc/data-objects-and-data-sources-ole.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zwischenablage](../mfc/clipboard.md)

