---
title: Dialogfelder in OLE
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
ms.openlocfilehash: 997bfc0bda05f5a2520c102cb38777b533bcef95
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685775"
---
# <a name="dialog-boxes-in-ole"></a>Dialogfelder in OLE

Während ein Benutzer eine OLE-fähige Anwendung ausführt, gibt es Zeiten, in denen die Anwendung Informationen vom Benutzer benötigt, um den Vorgang auszuführen. Die MFC-OLE-Klassen stellen eine Reihe von Dialogfeldern bereit, um die erforderlichen Informationen zu sammeln. In diesem Thema werden die Tasks aufgelistet, die von den OLE-Dialogfeldern und den zum Anzeigen dieser Dialogfelder benötigten Klassen behandelt werden. Ausführliche Informationen zu OLE-Dialogfeldern und den Strukturen, die zum Anpassen des Verhaltens verwendet werden, finden Sie unter [MFC-Referenz](../mfc/mfc-desktop-applications.md).

*Objekt einfügen*<br/>
In diesem Dialogfeld kann der Benutzer neu erstellte oder vorhandene Objekte in das Verbund Dokument einfügen. Außerdem kann der Benutzer auswählen, dass das Element als Symbol angezeigt wird, und die Befehls Schaltfläche "Symbol ändern" aktiviert. Dieses Dialogfeld wird angezeigt, wenn der Benutzer im Menü Bearbeiten die Option Objekt einfügen auswählt. Verwenden Sie die [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) -Klasse, um dieses Dialogfeld anzuzeigen. Beachten Sie, dass eine MDI-Anwendung nicht in sich selbst eingefügt werden kann. Eine Anwendung, die ein Container/Server ist, kann nur in sich selbst eingefügt werden, wenn es sich um eine SDI-Anwendung handelt.

*Sonderzeichen einfügen*<br/>
Mithilfe dieses Dialog Felds kann der Benutzer das Format steuern, das beim Einfügen von Daten in ein Verbund Dokument verwendet wird. Der Benutzer kann das Format der Daten auswählen, unabhängig davon, ob die Daten eingebettet oder verknüpft werden sollen und ob Sie als Symbol angezeigt werden sollen. Dieses Dialogfeld wird angezeigt, wenn der Benutzer im Menü Bearbeiten die Option Sonderzeichen einfügen auswählt. Verwenden Sie die [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) -Klasse, um dieses Dialogfeld anzuzeigen.

*Symbol "ändern"*<br/>
In diesem Dialogfeld können Benutzer auswählen, welches Symbol angezeigt wird, um das verknüpfte oder eingebettete Element darzustellen. Zeigen Sie dieses Dialogfeld an, wenn der Benutzer im Menü Bearbeiten die Option Symbol ändern auswählt, oder wählen Sie die Schaltfläche Symbol ändern in den Dialogfeldern speziell einfügen oder konvertieren aus. Sie sollten diese auch anzeigen, wenn der Benutzer das Dialogfeld Objekt einfügen öffnet und als Symbol anzeigen auswählt. Verwenden Sie die [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) -Klasse, um dieses Dialogfeld anzuzeigen.

*Umgebaut*<br/>
In diesem Dialogfeld können Benutzer den Typ eines eingebetteten oder verknüpften Elements ändern. Wenn Sie z. b. eine Metadatei in ein Verbund Dokument eingebettet haben und später eine andere Anwendung verwenden möchten, um die eingebettete Metadatendatei zu ändern, können Sie das Dialogfeld konvertieren verwenden. Dieses Dialogfeld wird normalerweise angezeigt, wenn Sie im Menü Bearbeiten auf *Objekttyp* Objekt klicken und dann im kaskadierenden Menü auf konvertieren klicken. Verwenden Sie die [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) -Klasse, um dieses Dialogfeld anzuzeigen. Führen Sie z. b. das MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md)aus.

*Links oder Update Verknüpfungen bearbeiten*<br/>
Im Dialogfeld Verknüpfungen bearbeiten kann der Benutzerinformationen zur Quelle eines verknüpften Objekts ändern. Im Dialogfeld "Links aktualisieren" werden die Quellen aller verknüpften Elemente im aktuellen Dialogfeld überprüft und ggf. das Dialogfeld "Links bearbeiten" angezeigt. Zeigen Sie das Dialogfeld Links bearbeiten an, wenn der Benutzer im Menü Bearbeiten die Option Links auswählt. Das Dialogfeld Links aktualisieren wird normalerweise angezeigt, wenn ein Verbund Dokument zum ersten Mal geöffnet wird. Abhängig von dem Dialogfeld, das Sie anzeigen möchten, können Sie entweder die [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) -oder die [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) -Klasse verwenden.

*Server ausgelastet, oder der Server reagiert nicht.*<br/>
Das Dialogfeld Server ausgelastet wird angezeigt, wenn der Benutzer versucht, ein Element zu aktivieren, und der Server die Anforderung zurzeit nicht verarbeiten kann. Dies ist in der Regel der Fall, weil der Server von einem anderen Benutzer oder einer anderen Aufgabe verwendet wird. Das Dialogfeld Server antwortet nicht wird angezeigt, wenn der Server nicht auf die Aktivierungs Anforderung antwortet. Diese Dialogfelder werden über `COleMessageFilter` auf der Grundlage einer Implementierung der OLE-Schnittstelle `IMessageFilter` angezeigt, und der Benutzer kann entscheiden, ob die Aktivierungs Anforderung erneut versucht werden soll. Verwenden Sie die [colebusydialog](../mfc/reference/colebusydialog-class.md) -Klasse, um dieses Dialogfeld anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE](../mfc/ole-in-mfc.md)
