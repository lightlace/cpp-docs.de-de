---
title: 'Zwischenablage: Daten kopieren und einfügen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Clipboard, copying data to
- Clipboard, pasting
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4756da7459f3e584dd02b882f5c790412c095561
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929467"
---
# <a name="clipboard-copying-and-pasting-data"></a>Zwischenablage: Daten kopieren und einfügen
Dieses Thema beschreibt die Arbeitsschritte, die mindestens erforderlich, kopieren und Einfügen aus der Zwischenablage in der OLE-Anwendung zu implementieren. Es wird empfohlen, Sie lesen die [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Themen, bevor Sie fortfahren.  
  
 Bevor Sie implementieren können, kopieren oder einfügen, müssen Sie zuerst Funktionen zum Kopieren, Ausschneiden und Einfügen-Optionen im Menü Bearbeiten behandeln bereitstellen.  
  
##  <a name="_core_copying_or_cutting_data"></a> Kopieren oder Ausschneiden von Daten  
  
#### <a name="to-copy-data-to-the-clipboard"></a>Um Daten in die Zwischenablage kopieren  
  
1.  Bestimmen Sie, ob die Daten kopiert werden systemeigene Daten oder eine eingebettete oder verknüpfte Element.  
  
    -   Wenn die Daten eingebettet oder verknüpft ist, erhalten Sie einen Zeiger auf die `COleClientItem` -Objekt, das ausgewählt wurde.  
  
    -   Wenn die Daten systemeigene sind und die Anwendung ein Server ist, erstellen Sie ein neues Objekt abgeleitet `COleServerItem` , die die ausgewählten Daten enthält. Erstellen Sie andernfalls eine `COleDataSource` Objekt für die Daten.  
  
2.  Rufen Sie des ausgewählten Elements `CopyToClipboard` Memberfunktion.  
  
3.  Wenn der Benutzer einen Vorgang Ausschneiden anstelle eines Kopiervorgangs ausgewählt haben, löschen Sie die ausgewählten Daten aus Ihrer Anwendung.  
  
 Ein Beispiel für diese Sequenz finden Sie unter der `OnEditCut` und `OnEditCopy` Funktionen in der MFC-OLE-Beispielprogramme [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md). Beachten Sie, dass diese Beispiele verwaltet einen Zeiger auf die Daten aktuell ausgewählten Schritt 1 bereits abgeschlossen ist.  
  
##  <a name="_core_pasting_data"></a> Einfügen von Daten  
 Einfügen von Daten ist komplizierter als das Kopieren, da das Format in das Einfügen von Daten in Ihrer Anwendung verwenden auswählen müssen.  
  
#### <a name="to-paste-data-from-the-clipboard"></a>Daten aus der Zwischenablage einfügen  
  
1.  Implementieren Sie in Ihrer Ansichtsklasse `OnEditPaste` zum Auswählen der Option "Einfügen" aus dem Menü Bearbeiten-Benutzer zu verarbeiten.  
  
2.  In der `OnEditPaste` funktionieren, erstellen Sie eine `COleDataObject` Objekt, und rufen die `AttachClipboard` Memberfunktion versucht, dieses Objekt an den Daten in die Zwischenablage zu verknüpfen.  
  
3.  Rufen Sie `COleDataObject::IsDataAvailable` zu überprüfen, ob ein bestimmtes Format verfügbar ist.  
  
     Alternativ können Sie `COleDataObject::BeginEnumFormats` nach anderen Formaten gesucht werden soll, bis Sie am besten für Ihre Anwendung finden.  
  
4.  Führen Sie das Einfügen des Formats.  
  
 Ein Beispiel dafür, wie dies funktioniert, finden Sie in der Implementierung von der `OnEditPaste` Memberfunktionen in der Ansichtsklassen in MFC OLE Beispielprogramme [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md).  
  
> [!TIP]
>  Der Hauptvorteil der Trennung der Einfügevorgang in eine eigene Funktion ist, dass der gleiche einfügen-Code verwendet werden kann, wenn Daten in der Anwendung während eines Drag & Drop-Vorgangs gelöscht werden. Wie bei OCLIENT und HIERSVR Ihre `OnDrop` Funktionsaufruf kann auch `DoPasteItem`, Einfügevorgänge implementieren geschriebenen Codes wiederverwenden.  
  
 Um die Option "Inhalte einfügen" im Menü Bearbeiten behandeln zu können, finden Sie im Thema [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md).  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [OLE-Objekte und Daten Datenquellen und uniform Data transfer](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE- Drag & drop](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

