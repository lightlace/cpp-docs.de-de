---
title: OLE allgemeine Dialogfeldklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6ef5a7aed288331322243d316dde58d9f36cbd9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430422"
---
# <a name="ole-common-dialog-classes"></a>OLE-Common-Dialogfeldklassen

Diese Klassen behandeln allgemeine OLE-Aufgaben durch Implementieren einer Reihe von OLE-Standarddialogfelder. Sie bieten auch eine einheitliche Benutzeroberfläche für die OLE-Funktionen.

[COleDialog](../mfc/reference/coledialog-class.md)<br/>
Häufige Anwendungsbereiche für alle OLE-Dialogfelder enthalten verwendet vom Framework. Alle Dialogfeldklassen in der Kategorie der Benutzeroberfläche werden von dieser Basisklasse abgeleitet. `COleDialog` kann nicht direkt verwendet werden.

[COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)<br/>
Objekt einfügen zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Einfügen von neuen OLE Verknüpfte oder eingebettete Elemente.

[COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)<br/>
Fügen Sie spezielle zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Implementieren des Befehls Inhalte einfügen bearbeiten.

[COleLinksDialog](../mfc/reference/colelinksdialog-class.md)<br/>
Verknüpfungen bearbeiten zeigt das Dialogfeld an, die Standardbenutzeroberfläche zum Ändern von Informationen zu verknüpften Elementen.

[COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)<br/>
Zeigt das Dialogfeld "Symbol ändern", die Standardbenutzeroberfläche für ändern, das ein OLE zugeordnete Symbol eingebettet, oder verknüpftes Element an.

[COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)<br/>
Zeigt das Dialogfeld konvertieren, die Standardbenutzeroberfläche für die Konvertierung von OLE-Elementen von einem Typ in einen anderen.

[COlePropertiesDialog](../mfc/reference/colepropertiesdialog-class.md)<br/>
Kapselt das Windows allgemeine OLE-Eigenschaften-Dialogfeld. OLE-Eigenschaften-Standarddialogfelder bieten eine einfache Möglichkeit zum Anzeigen und ändern die Eigenschaften eines Elements des OLE-Dokument in Übereinstimmung mit den Windows-Standards.

[COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)<br/>
Update zeigt das Dialogfeld an, die Standardbenutzeroberfläche für alle Links in einem Dokument zu aktualisieren. Das Dialogfeld enthält eine Statusanzeige, um anzugeben, wie nahe die Updateprozedur abgeschlossen ist.

[COleChangeSourceDialog](../mfc/reference/colechangesourcedialog-class.md)<br/>
Quelle ändern zeigt das Dialogfeld an, die Standardbenutzeroberfläche für das Ändern der Ziel- oder eines Links.

[COleBusyDialog](../mfc/reference/colebusydialog-class.md)<br/>
Zeigt die Server ausgelastet "und" Server nicht geantwortet-Dialogfelder, die Standardbenutzeroberfläche Aufrufe für ausgelastete Anwendungen zu behandeln. Normalerweise automatisch vom angezeigt, die `COleMessageFilter` Implementierung.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

