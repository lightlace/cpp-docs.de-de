---
title: OLE-Common-Dialogfeldklassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- dialog classes [MFC], OLE
- OLE common dialog classes [MFC]
- common dialog classes [MFC]
ms.assetid: 706526ae-f94f-4909-a0f8-6b5fe954fd97
ms.openlocfilehash: d34c141fc9a2b53eab6a4c0b0ce1799ff5243d84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186390"
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
