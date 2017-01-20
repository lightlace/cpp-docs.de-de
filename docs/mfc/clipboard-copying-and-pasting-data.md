---
title: "Zwischenablage: Daten kopieren und einf&#252;gen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zwischenablage, Kopieren von Daten nach"
  - "Zwischenablage, Einfügen"
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zwischenablage: Daten kopieren und einf&#252;gen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieses Thema beschreibt die minimale Arbeit, die erforderlich ist, um das Kopieren zu und Einfügen aus der Zwischenablage in der OLE\-Anwendung zu implementieren.  Es wird empfohlen, die [Datenobjekte und Datenquellen \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) Themen lesen, bevor Sie fortfahren.  
  
 Bevor Sie das Kopieren oder Einfügen implementieren können, müssen Sie zuerst Funktionen bereitstellen, um die Zwischenablage, Schnitt\- und Pastenoptionen im Menü Bearbeiten zu behandeln.  
  
##  <a name="_core_copying_or_cutting_data"></a> Kopieren oder Schnittparameter  
  
#### Um Daten in die Zwischenablage kopieren  
  
1.  Bestimmen Sie, ob die Daten ist oder systemeigene Daten ist ein verknüpftes oder eingebettetes Element kopiert wird.  
  
    -   Wenn die Daten eingebettet bzw. verknüpft werden, rufen Sie einen Zeiger auf das `COleClientItem`\-Objekt, das ausgewählt wurde.  
  
    -   Wenn die Daten angehören und die Anwendung ein Server ist, erstellen Sie ein neues Objekt, das von `COleServerItem` abgeleitet wird, das die ausgewählten Daten enthält.  Andernfalls erstellen Sie ein `COleDataSource`\-Objekt für die Daten.  
  
2.  Rufen Sie die ausgewählten `CopyToClipboard`\-Memberfunktion des Elements auf.  
  
3.  Wenn der Benutzer ein Ausschneidevorgang anstelle eines Kopiervorgangs auswählte, löschen Sie die ausgewählten Daten von der Anwendung.  
  
 Um ein Beispiel dieser Sequenz zu finden, lesen Sie die **OnEditCut** und **OnEditCopy** in den Funktionen auch [OCLIENT](../top/visual-cpp-samples.md) und [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE.  Beachten Sie, dass diese Beispiele einen Zeiger auf den derzeit ausgewählten Daten warten, sodass Schritt 1 bereits abgeschlossen.  
  
##  <a name="_core_pasting_data"></a> Einfügen von Daten  
 Daten einzufügen ist schwieriger, als es kopiert, da Sie den Stil auswählen müssen, um zu verwenden, wenn Sie die Daten in die Anwendung einfügen.  
  
#### Um Daten aus der Zwischenablage einfügen  
  
1.  In der Ansichtsklasse die **OnEditPaste**, um von Benutzern zu behandeln, die die Pastenoption im Menü Bearbeiten auswählen.  
  
2.  In der **OnEditPaste**\-Funktion erstellen Sie ein `COleDataObject`\-Objekt und rufen Sie dessen `AttachClipboard`\-Memberfunktion auf, um das Objekt an Daten in der Zwischenablage zu verknüpfen.  
  
3.  Rufen Sie `COleDataObject::IsDataAvailable` auf, um zu überprüfen, ob ein bestimmtes Format verfügbar ist.  
  
     Alternativ können Sie `COleDataObject::BeginEnumFormats` verwenden, um nach anderen Formaten finden, bis Sie finden ein, das die meisten Ihrer Anwendung verarbeiten.  
  
4.  Führen Sie das Einfügen des Stils aus.  
  
 Ein Beispiel, wie dies funktioniert, finden Sie in der Implementierung **OnEditPaste** in den Memberfunktionen Ansichtsklassen, die in den auch [OCLIENT](../top/visual-cpp-samples.md) und [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE definiert werden.  
  
> [!TIP]
>  Der Hauptvorteil des Trennens des Einfügevorgangs in seine eigene Features ist, dass die gleiche Pastencode verwendet werden, wenn Daten in die Anwendung während eines Drag & Drop\-Vorgangs abgelegt werden.  Wie im OCLIENT\-Menü und in HIERSVR, kann die `OnDrop`\-Funktion auch **DoPasteItem** aufrufen und Code wiederverwenden, der zum Implementieren Einfügevorgängen geschrieben wird.  
  
 Um die Inhalte einfügen\-Option im Menü Bearbeiten zu behandeln, finden Sie im Thema [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md).  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)  
  
-   [OLE\-Datenobjekte und Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [Drag & Drop](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## Siehe auch  
 [Zwischenablage: Verwenden des OLE\-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)