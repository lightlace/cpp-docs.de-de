---
title: 'Zwischenablage: Daten kopieren und einfügen | Microsoft-Dokumentation'
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
ms.openlocfilehash: 8f4a3ba23fbf6e9465d78b04fcd79758c7cae525
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060228"
---
# <a name="clipboard-copying-and-pasting-data"></a>Zwischenablage: Daten kopieren und einfügen

Dieses Thema beschreibt die minimale Arbeit erforderlich, zu kopieren und Einfügen aus der Zwischenablage in einer OLE-Anwendung zu implementieren. Es wird empfohlen, die Sie lesen die [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md) Themen, bevor Sie fortfahren.

Bevor Sie implementieren können, kopieren oder einfügen, müssen Sie die Funktionen zum Verarbeiten der kopieren, Ausschneiden und Einfügen-Optionen auf das Menü "Bearbeiten" zunächst bereitstellen.

##  <a name="_core_copying_or_cutting_data"></a> Kopieren oder Ausschneiden von Daten

#### <a name="to-copy-data-to-the-clipboard"></a>Um Daten in die Zwischenablage zu kopieren.

1. Bestimmen Sie, ob die Daten kopiert werden systemeigene Daten oder ein eingebettetes oder verknüpftes Element ist.

   - Wenn die Daten eingebettet oder verknüpft ist, erhalten Sie einen Zeiger auf die `COleClientItem` -Objekt, das ausgewählt wurde.

   - Wenn die Daten sind auf native und die Anwendung ein Server ist, erstellen Sie ein neues Objekt abgeleitet `COleServerItem` , die die ausgewählten Daten enthält. Erstellen Sie andernfalls eine `COleDataSource` Objekt für die Daten.

1. Rufen Sie des ausgewählten Elements `CopyToClipboard` Member-Funktion.

1. Wenn der Benutzer eine Ausschneiden-Operation anstelle eines Kopiervorgangs ausgewählt haben, löschen Sie die ausgewählten Daten aus Ihrer Anwendung.

Ein Beispiel für diese Sequenz finden Sie unter den `OnEditCut` und `OnEditCopy` Funktionen in der MFC-OLE-Beispielprogramme [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md). Beachten Sie, dass diese Beispiele verwalten einen Zeiger auf die ausgewählten Daten aus, damit Schritt 1 bereits abgeschlossen wurde.

##  <a name="_core_pasting_data"></a> Einfügen von Daten

Einfügen von Daten ist komplizierter als das Kopieren, da Sie wählen Sie das Format, die Daten in Ihre Anwendung beim Einfügen müssen.

#### <a name="to-paste-data-from-the-clipboard"></a>Daten aus der Zwischenablage einfügen

1. Implementieren Sie in Ihrer Ansichtsklasse `OnEditPaste` auf Benutzer, die Auswahl der Option "Einfügen" aus dem Menü "Bearbeiten" zu verarbeiten.

1. In der `OnEditPaste` funktioniert, erstellen Sie eine `COleDataObject` Objekt, und rufen die `AttachClipboard` Memberfunktion versucht, dieses Objekt mit den Daten in der Zwischenablage zu verknüpfen.

1. Rufen Sie `COleDataObject::IsDataAvailable` zu überprüfen, ob ein bestimmtes Format verfügbar ist.

   Alternativ können Sie `COleDataObject::BeginEnumFormats` nach anderen Formaten gesucht werden soll, bis Sie am besten zu Ihrer Anwendung finden.

1. Führen Sie das Einfügen des Formats.

Ein Beispiel, wie dies funktioniert, finden Sie die Implementierung von der `OnEditPaste` Memberfunktionen in der Ansichtsklassen definiert, die in den MFC-OLE-Beispielprogrammen [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md).

> [!TIP]
>  Der Hauptvorteil der Trennung des Einfügevorgangs in eine eigene Funktion ist, dass der gleiche fügen Sie Code verwendet werden kann, wenn Daten in Ihrer Anwendung während eines Drag & Drop-Vorgangs gelöscht werden. Wie bei OCLIENT und HIERSVR Ihre `OnDrop` Funktionsaufruf kann auch `DoPasteItem`, Wiederverwendung von Code geschrieben, um die einfügen-Vorgänge zu implementieren.

Behandeln Sie die Option "Inhalte einfügen" auf das Menü "Bearbeiten" finden Sie unter dem Thema [Dialogfelder in OLE](../mfc/dialog-boxes-in-ole.md).

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Hinzufügen anderer Formate](../mfc/clipboard-adding-other-formats.md)

- [OLE-Objekte und Daten-Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)

- [OLE- Drag & drop](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Siehe auch

[Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

