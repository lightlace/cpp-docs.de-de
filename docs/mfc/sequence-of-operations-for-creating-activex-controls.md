---
title: Reihenfolge der Operationen zur Erstellung von ActiveX-Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: caf4c74f2263505ad5d7112021003f92c85a4b84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380369"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>Operationssequenz zur Erstellung von ActiveX-Steuerelementen
Die folgende Tabelle zeigt Ihre Rolle und das Framework beim Erstellen von ActiveX-Steuerelementen (früher OLE-Steuerelemente).  
  
### <a name="creating-activex-controls"></a>Erstellen von ActiveX-Steuerelementen  
  
|Aufgabe|Sie tun|Das Framework ermöglicht|  
|----------|------------|------------------------|  
|Erstellen Sie ein ActiveX-Steuerelement-Framework.|Führen Sie die MFC-ActiveX-Steuerelement-Assistenten zum Erstellen des Steuerelements. Geben Sie die gewünschten Optionen auf den Optionsseiten. Optionen umfassen den Typ und den Namen des Steuerelements im Projekt, Lizenzierung, Klassifizierung und eine Methode zum Feld.|Die MFC-ActiveX-Steuerelement-Assistent erstellt die Dateien für ein ActiveX-Steuerelement mit Grundfunktionen, einschließlich Quelldateien für Ihre Anwendung, die Steuerelement, und die Eigenschaftenseite oder die Seiten; eine Ressourcendatei; eine Projektdatei; und andere, alle zugeschnitten sind, entsprechend Ihren Anforderungen.|  
|Finden Sie, was das Steuerelement und der ActiveX-Steuerelement-Assistent bieten, ohne eine eigene Codezeile hinzuzufügen.|Erstellen Sie das ActiveX-Steuerelement und Testen sie das mit Internet Explorer oder die [TSTCON Beispiel](../visual-cpp-samples.md).|Das ausgeführte Steuerelement hat die Möglichkeit, angepasst und verschoben werden. Sie hat auch ein **über das** -Methode (wenn es sich um eine ausgewählt), die aufgerufen werden können.|  
|Implementieren Sie die Methoden und Eigenschaften des Steuerelements.|Implementieren Sie die Steuerelement-spezifischen Methoden und Eigenschaften, durch Hinzufügen von Memberfunktionen, um eine verfügbar gemachte Schnittstelle auf die Daten des Steuerelements bereitzustellen. Fügen Sie Membervariablen zum Halten von Datenstrukturen und verwenden Ereignishandler, um Ereignisse auszulösen, wenn Sie bestimmen.|Das Framework wurde bereits definiert eine Zuordnung zur Unterstützung des Steuerelements-Ereignisse, Eigenschaften und Methoden, lassen Sie den Schwerpunkt auf wie die Eigenschaften und Methoden implementiert werden. Die Standardseite für die Eigenschaft sichtbar ist, und eine Standardmethode für das Dialogfeld Info angegeben wird.|  
|Erstellen Sie das Steuerelement auf der Seite oder Seiten.|Verwenden Sie die Visual C++-Ressourcen-Editoren, um visuell Eigenschaftenseiten-Schnittstelle des Steuerelements bearbeiten:<br /><br /> – Erstellen Sie zusätzliche Eigenschaftenseiten.<br />-Erstellen Sie und bearbeiten Sie, Bitmaps, Symbole und Cursor.<br /><br /> Sie können auch die Eigenschaftenseiten der Dialog-Editor testen.|Die Standardressourcendatei, die vom MFC-Anwendungs-Assistenten erstellte stellt viele der Ressourcen, die Sie benötigen. Visual C++ können Sie vorhandene Ressourcen zu bearbeiten und neue Ressourcen einfach und visuell hinzufügen.|  
|Testen Sie die Ereignisse, Methoden und Eigenschaften des Steuerelements.|Erstellen Sie das Steuerelement neu und verwenden Sie den Testcontainer testen, ob die Handler ordnungsgemäß funktioniert.|Die Methoden des Steuerelements aufrufen können und bearbeiten seine Eigenschaften, die über die Benutzeroberfläche für die Eigenschaftenseite oder Testcontainer. Verwenden Sie darüber hinaus Testcontainer überwachen Ereignisse, die ausgelöst wird, aus dem Steuerelement und Benachrichtigungen, die vom Container des Steuerelements empfangen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)

