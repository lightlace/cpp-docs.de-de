---
title: "Dialogfelder in OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Dialogfelder"
  - "Dialogfelder, Informationen über Dialogfelder"
  - "Dialogfelder, OLE"
  - "Einfügen eines Objekts"
  - "MFC-Dialogfelder, OLE-Dialogfelder"
  - "OLE-Dialogfelder"
  - "OLE-Dialogfelder, Informationen über OLE-Dialogfelder"
ms.assetid: 73c41eb8-738a-4d02-9212-d3395bb09a3a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Dialogfelder in OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Während ein Benutzer eine OLE\-aktivierte Anwendung ausgeführt wird, gibt jedoch Situationen, in die Anwendung Informationen vom Benutzer benötigt, um die Arbeit durchzuführen.  Die Klassen MFC\-OLE stellen einige Dialogfelder, um die erforderlichen Informationen zu erfassen.  Dieses Thema führt die Aufgaben auf, die von der OLE\-Dialogfelder behandelt und die Klassen, die erforderlich sind, um diese Dialogfelder anzuzeigen.  Ausführliche Informationen über OLE\-Dialogfelder sowie von Strukturen, die verwendet werden, um deren Verhalten anzupassen, finden Sie unter [MFC\-Referenz](../mfc/mfc-desktop-applications.md).  
  
 *Objekt einfügen*  
 Dieses Dialogfeld ermöglicht den Benutzern neu erstellten oder vorhandenen Objekten Einfüge\- in das Verbunddokument erfolgen.  Außerdem können Benutzer, um zu wählen, um das Element als Symbol anzuzeigen und die Änderungs\-Symbolbefehlsschaltfläche.  Zeigen Sie dieses Dialogfeld, wenn der Benutzer EINFG\-Objekt im Menü Bearbeiten auswählt.  Verwenden Sie die [COleInsertDialog](../mfc/reference/coleinsertdialog-class.md)\-Klasse, um dieses Dialogfeld anzuzeigen.  Beachten Sie, dass Sie sich in eine MDI\-Anwendung nicht einfügen können.  Eine Anwendung, die ein Container\/Server ist, kann nicht in sich eingefügt werden, es sei denn, es ist eine SDI\-Anwendung ist.  
  
 *Inhalte einfügen*  
 Dieses Dialogfeld ermöglicht dem Benutzer, die das Format zu steuern, das wenn Daten in ein Verbunddokument verwendet wird, einfügt.  Der Benutzer kann das Format der Daten auswählen, ob die Daten eingebettet bzw. verknüpft und ob es als Symbol anzeigt.  Zeigen Sie dieses Dialogfeld, wenn der Benutzer im Menü Bearbeiten Inhalte einfügen auswählt.  Verwenden Sie die [COlePasteSpecialDialog](../mfc/reference/colepastespecialdialog-class.md)\-Klasse, um dieses Dialogfeld anzuzeigen.  
  
 *Ändern Sie Symbol*  
 Dieses Dialogfeld ermöglicht dem Benutzer, um auszuwählen, welche Symbol angezeigt wird, das verknüpfte oder eingebettete Element darzustellen.  Zeigen Sie dieses Dialogfeld, wenn der Benutzer Änderungs\-Symbol im Menü Bearbeiten auswählt oder die Änderungs\-Symbolschaltfläche entweder in Inhalte einfügen auswählt an oder konvertieren Sie Dialogfelder.  Zeigen Sie diese ebenfalls an, wenn der Benutzer das EINFG\-Objektdialogfeld öffnet und Anzeige als Symbol auswählen.  Verwenden Sie die [COleChangeIconDialog](../mfc/reference/colechangeicondialog-class.md)\-Klasse, um dieses Dialogfeld anzuzeigen.  
  
 *Konvertieren*  
 Dieses Dialogfeld ermöglicht dem Benutzer, die den Typ eines eingebetteten oder verknüpften Elements ändern.  Wenn Sie beispielsweise eine Metadatei in einem Verbunddokument eingebettet und später eine andere Anwendung haben verwenden möchten, die eingebettete Metadatei zu ändern, können Sie das Bekehrtdialogfeld verwenden.  Dieses Dialogfeld wird üblicherweise angezeigt, indem *auf Elementtyp*\-Objekt im Menü Bearbeiten, und klicken Sie dann im Untermenü klickt und auf verschiedenen klickt.  Verwenden Sie die [COleConvertDialog](../mfc/reference/coleconvertdialog-class.md)\-Klasse, um dieses Dialogfeld anzuzeigen.  Ein Beispiel führen Sie das Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE aus.  
  
 *Bearbeiten Sie Links oder aktualisieren Sie Links*  
 Das Bearbeitungs\-Linkdialogfeld kann der Benutzer die Änderungsinformationen zur Quelle eines verknüpften Objekts.  Das Update\-Linkdialogfeld überprüft die Quellen aller verknüpften Elemente im aktuellen Dialogfeld und das Bearbeitungs\-Linkdialogfeld ggf. an.  Zeigen Sie das Bearbeitungs\-Linkdialogfeld an, wenn der Benutzer Links im Menü Bearbeiten auswählt.  Das Update\-Linkdialogfeld Regel wird angezeigt, wenn ein Verbunddokument zuerst geöffnet ist.  Verwenden Sie entweder [COleLinksDialog](../mfc/reference/colelinksdialog-class.md) oder die [COleUpdateDialog](../mfc/reference/coleupdatedialog-class.md)\-Klasse, abhängig von der verwendeten Dialogfeld Sie anzeigen möchten.  
  
 *Server ausgelastet oder nicht reagierender Server*  
 Das ausgelastete Dialogfeld des Servers wird angezeigt, wenn der Benutzer versucht, ein Element aktivieren und der Server einfach nicht möglich ist, der die Anforderung behandelt wird, normalerweise, da der Server durch einen Benutzer oder anderen Aufgabe verwendet wird.  Das Reaktionsdialogfeld des Servers nicht angezeigt wird, wenn der Server nicht auf die eine Aktivierungsanforderung reagiert.  Diese Dialogfelder werden über `COleMessageFilter`, in einer Implementierung der OLE\-Schnittstelle **IMessageFilter** angezeigt, und der Benutzer kann festlegen, ob die Aktivierung anfordern erneut versucht.  Verwenden Sie die [COleBusyDialog](../mfc/reference/colebusydialog-class.md)\-Klasse, um dieses Dialogfeld anzuzeigen.  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [OLE](../mfc/ole-in-mfc.md)