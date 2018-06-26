---
title: Dialogfelder in OLE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], OLE dialog boxes
- OLE dialog boxes
- dialog boxes
- OLE dialog boxes [MFC], about OLE dialog boxes
- dialog boxes [MFC], about dialog boxes
- dialog boxes [MFC], OLE
- Insert object
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe7f9b4b97fd17e73c3dd9f113a87d8f087b93c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929662"
---
# <a name="dialog-boxes-in-ole"></a>Dialogfelder in OLE
Während ein Benutzer eine OLE-fähige Anwendung ausgeführt wird, stehen die Zeiten, wenn die Anwendung Informationen vom Benutzer benötigt, um den Vorgang durchzuführen. Die MFC-OLE-Klassen bieten eine Reihe von Dialogfeldern, um die erforderlichen Informationen zu sammeln. Dieses Thema listet die Aufgaben, die von der OLE-Dialogfelder behandelt und den Klassen erforderlich, um diese Dialogfelder angezeigt. Weitere Informationen zu OLE-Dialogfelder und die Strukturen verwendet, um ihr Verhalten anzupassen, finden Sie unter [MFC-Referenz](../mfc/mfc-desktop-applications.md).  
  
 *Objekt einfügen*  
 Dieses Dialogfeld ermöglicht den Benutzer, einfügen, die neu erstellt oder vorhandene Objekte in Verbunddokuments. Außerdem kann der Benutzer festlegen, dass das Element als Symbol angezeigt und ermöglicht die Befehlsschaltfläche "Symbol ändern". Zeigen Sie dieses Dialogfeld an, wenn der Benutzer ein Objekt einfügen aus dem Menü Bearbeiten auswählt. Verwenden der [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md) Klasse, um das Dialogfeld anzuzeigen. Beachten Sie, dass Sie eine MDI-Anwendung in sich selbst einfügen können. Eine Anwendung, einem Container/Server kann nicht in sich selbst eingefügt werden, wenn sie eine SDI-Anwendung ist.  
  
 *Fügen Sie spezielle*  
 Dieses Dialogfeld ermöglicht den Benutzer das Einfügen von Daten in ein Verbunddokument verwendete Format zu steuern. Der Benutzer kann auswählen, das Format der Daten, ob einbetten oder verknüpfen die Daten, ob er als Symbol angezeigt. Zeigen Sie dieses Dialogfeld an, wenn Benutzer Inhalte einfügen aus dem Menü Bearbeiten. Verwenden der [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md) Klasse, um das Dialogfeld anzuzeigen.  
  
 *"Symbol ändern"*  
 Öffnen Sie das Dialogfeld ermöglicht den Benutzer auszuwählen, welches Symbol angezeigt wird, um das Element verknüpfte oder eingebettete darstellen. Zeigen Sie dieses Dialogfeld an, wenn der Benutzer "Symbol ändern" aus dem Menü Bearbeiten wählt oder die Schaltfläche "Symbol ändern", in der Inhalte einfügen oder Convert-Dialogfelder auswählt. Zeigen Sie es auch wenn der Benutzer das Dialogfeld "Objekt einfügen Öffnet", und als Symbol angezeigt wählt. Verwenden der [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md) Klasse, um das Dialogfeld anzuzeigen.  
  
 *Konvertieren*  
 Öffnen Sie das Dialogfeld ermöglicht den Benutzer, der Typ eines Elements eingebettete oder verknüpfte ändern. Wenn Sie eine Metadatei in einem zusammengesetzten Dokument eingebettet haben und später eine andere Anwendung zu verwenden, um die eingebetteten Metadatei ändern möchten, können Sie das Dialogfeld "konvertieren" verwenden. Dieses Dialogfeld wird normalerweise angezeigt, wenn Sie *Konfigurationselementtyp* Objekt im Menü Bearbeiten und dann im Untermenü auf konvertieren. Verwenden der [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md) Klasse, um das Dialogfeld anzuzeigen. Führen Sie ein Beispiel, das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md).  
  
 *Links zum Bearbeiten oder Update-Links*  
 Das Dialogfeld "Verknüpfungen bearbeiten" ermöglicht des Benutzers Informationen über die Quelle eines verknüpften Objekts ändern. Das Dialogfeld Update Links überprüft die Quellen für die verknüpften Elemente im aktuellen Dialogfeld und zeigt das Dialogfeld "Verknüpfungen bearbeiten" an, falls erforderlich. Das Dialogfeld "Verknüpfungen bearbeiten" angezeigt, wenn Benutzer Verknüpfungen aus dem Menü Bearbeiten. Das Dialogfeld Update Links wird in der Regel angezeigt, wenn ein Verbunddokument erstmalig geöffnet wird. Verwenden Sie entweder die [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) oder [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md) Klasse, abhängig vom Dialogfeld, das Sie anzeigen möchten.  
  
 *Server ist ausgelastet oder Server reagiert nicht*  
 Das Dialogfeld "Server ausgelastet" wird angezeigt, wenn der Benutzer versucht, ein Element zu aktivieren, und der Server momentan nicht ist auf die Anforderung behandelt, in der Regel verwendet werden, da der Server ist von einem anderen Benutzer verwendet oder Aufgabe. Der Server antwortet nicht-Dialogfeld wird angezeigt, wenn der Server nicht auf die Aktivierungsanfrage überhaupt reagiert. Diese Dialogfelder werden angezeigt, über `COleMessageFilter`basierend auf einer Implementierung der OLE-Schnittstelle `IMessageFilter`, und der Benutzer kann entscheiden, ob die Aktivierungsanfrage erneut zu versuchen. Verwenden der [COleBusyDialog](../mfc/reference/colebusydialog-class.md) Klasse, um das Dialogfeld anzuzeigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE](../mfc/ole-in-mfc.md)

