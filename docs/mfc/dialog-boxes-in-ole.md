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
ms.openlocfilehash: 53e802e973ca78619252fcc4100a7cc50009f2ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618506"
---
# <a name="dialog-boxes-in-ole"></a>Dialogfelder in OLE

Wenn ein Benutzer eine OLE-fähige Anwendung ausgeführt wird, gibt es Zeiten, wenn die Anwendung Informationen des Benutzers benötigt, um den Vorgang auszuführen. Die MFC-OLE-Klassen stellen eine Reihe von Dialogfeldern, um die erforderlichen Informationen zu sammeln. Dieses Thema enthält die Aufgaben, die von der OLE-Dialogfelder behandelt und die Klassen, die zum Anzeigen dieser Dialogfelder erforderlich sind. Weitere Informationen zu OLE-Dialogfelder und Strukturen verwendet, um ihr Verhalten anzupassen, finden Sie unter [MFC-Referenz](../mfc/mfc-desktop-applications.md).

*Objekt einfügen*<br/>
Dieses Dialogfeld ermöglicht dem Benutzer einfügen, die neu erstellt oder vorhandene Objekte in der Verbunddokument. Außerdem kann der Benutzer festlegen, dass das Element als Symbol angezeigt und können die Befehlsschaltfläche Symbol ändern. Zeigen Sie dieses Dialogfeld an, wenn der Benutzer ein Objekt einfügen aus dem Menü "Bearbeiten" auswählt. Verwenden der [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) Klasse, um das Dialogfeld anzuzeigen. Beachten Sie, dass eine MDI-Anwendung kann nicht in sich selbst eingefügt. Eine Anwendung, die ein Container/Server kann nicht in sich selbst eingefügt werden, es sei denn, es einer SDI-Anwendung ist.

*Inhalte einfügen*<br/>
Dieses Dialogfeld ermöglicht den Benutzer, das beim Einfügen von Daten in einem Verbunddokument verwendete Format zu steuern. Der Benutzer kann auswählen, das Format der Daten angibt, ob einbetten oder verknüpfen die Daten und angibt, ob es als Symbol anzuzeigen. Zeigen Sie dieses Dialogfeld an, wenn der Benutzer über das Menü "Bearbeiten" Inhalte einfügen auswählt. Verwenden der [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) Klasse, um das Dialogfeld anzuzeigen.

*Symbol ändern*<br/>
Dieses Dialogfeld ermöglicht den Benutzer auswählen, welches Symbol angezeigt wird, um das verknüpftes oder eingebettetes Element darstellen. Zeigen Sie dieses Dialogfeld an, wenn der Benutzer wählt aus dem Menü "Bearbeiten" Symbol ändern oder wählt die Schaltfläche "Symbol ändern" in der Inhalte einfügen oder Convert-Dialogfelder. Zeigen Sie an, wenn der Benutzer das Dialogfeld "Objekt einfügen Öffnet" und als Symbol wählt. Verwenden der [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) Klasse, um das Dialogfeld anzuzeigen.

*Konvertieren*<br/>
Dieses Dialogfeld ermöglicht den Benutzer, den Typ einer eingebetteten oder verknüpften Elements zu ändern. Wenn Sie eine Metadatei in einem Verbunddokument eingebettet haben und später eine andere Anwendung zu verwenden, um die eingebetteten Metadatei ändern möchten, können Sie z. B. das Dialogfeld "konvertieren" verwenden. Dieses Dialogfeld wird normalerweise angezeigt, indem Sie auf *Konfigurationselementtyp* Objekt auf das Menü "Bearbeiten" und dann auf klicken Sie im Untermenü auf konvertieren. Verwenden der [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) Klasse, um das Dialogfeld anzuzeigen. Führen Sie ein Beispiel, das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md).

*Links zum Bearbeiten oder aktualisieren Sie Links*<br/>
Das Dialogfeld "Verknüpfungen bearbeiten" ermöglicht des Benutzers, Informationen über die Quelle eines verknüpften Objekts zu ändern. Die Update-Links-Dialogfeld überprüft die Quellen für alle verknüpften Elemente im aktuellen Dialogfeld und zeigt das Dialogfeld "Verknüpfungen bearbeiten" an, falls erforderlich. Das Dialogfeld "Verknüpfungen bearbeiten" angezeigt, wenn der Benutzer Links aus dem Menü "Bearbeiten" auswählt. Das Update-Links-Dialogfeld wird in der Regel angezeigt, wenn einem Verbunddokument erstmalig geöffnet wird. Verwenden Sie entweder die [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) oder [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) Klasse, die abhängig vom Dialogfeld, das Sie anzeigen möchten.

*Server Busy "oder" Server antwortet nicht*<br/>
Das Dialogfeld "Server ausgelastet" angezeigt, wenn der Benutzer versucht, ein Element zu aktivieren, und der Server zurzeit nicht die Anforderung behandelt wird ist, in der Regel verwendet werden, da der Server ist von einem anderen Benutzer verwendet wird, oder Aufgabe. Das Dialogfeld "Server antwortet nicht" wird angezeigt, wenn der Server nicht auf die aktivierungsanforderung zu reagieren. Diese Dialogfelder werden angezeigt, über `COleMessageFilter`basierend auf einer Implementierung der OLE-Schnittstelle `IMessageFilter`, und der Benutzer kann entscheiden, ob die Anforderung zur Aktivierung erneut versuchen. Verwenden der [COleBusyDialog](../mfc/reference/colebusydialog-class.md) Klasse, um das Dialogfeld anzuzeigen.

## <a name="see-also"></a>Siehe auch

[Dialogfelder](../mfc/dialog-boxes.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE](../mfc/ole-in-mfc.md)

