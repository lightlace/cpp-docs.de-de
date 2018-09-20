---
title: Reihenfolge der Operationen zur Erstellung von ActiveX-Steuerelementen | Microsoft-Dokumentation
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
ms.openlocfilehash: 2d794b8bf762503900dad18c7457c31101ea6d62
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377713"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>Operationssequenz zur Erstellung von ActiveX-Steuerelementen

Die folgende Tabelle zeigt Ihre Rolle und des Frameworks, bei der Erstellung von ActiveX-Steuerelementen (früher als OLE-Steuerelemente).

### <a name="creating-activex-controls"></a>Erstellen von ActiveX-Steuerelementen

|Aufgabe|Sie tun|Das Framework ermöglicht|
|----------|------------|------------------------|
|Erstellen Sie ein Framework für ActiveX-Steuerelement.|Führen Sie die MFC-ActiveX-Steuerelement-Assistent um das Steuerelement zu erstellen. Geben Sie die gewünschten Optionen auf den Optionsseiten. Unter anderem den Datentyp und den Namen des Steuerelements in das Projekt, Lizenzierung, Unterklassen und eine im Info-Methode.|Die MFC-ActiveX-Steuerelement-Assistent erstellt die Dateien für ein ActiveX-Steuerelement mit grundlegender Funktionalität, einschließlich der Quelldateien für Ihre Anwendung, den-Steuerelement, und die auf der Seite oder Seiten; eine Ressourcendatei; eine Projektdatei; und anderen Benutzern, alle Ihren Anforderungen entsprechend angepasst.|
|Sehen Sie, was das Steuerelement und der ActiveX-Steuerelement-Assistent bieten, ohne eine Zeile mit Ihren eigenen Code hinzuzufügen.|Erstellen Sie das ActiveX-Steuerelement und Testen Sie es mit Internet Explorer oder die [TSTCON Beispiel](../visual-cpp-samples.md).|Das ausgeführte Steuerelement kann die Größe verändert und verschoben werden. Es verfügt auch über eine **Infofeld** -Methode (sofern ausgewählt), die aufgerufen werden kann.|
|Implementieren von Methoden und Eigenschaften des Steuerelements.|Implementieren Sie Ihre steuerelementspezifische Methoden und Eigenschaften, durch das Hinzufügen von Memberfunktionen, um eine verfügbar gemachte Schnittstelle, die Daten des Steuerelements bereitzustellen. Hinzufügen von Membervariablen zum Speichern von Datenstrukturen, und verwenden Sie Ereignishandler, um Ereignisse auszulösen, wenn Sie bestimmen.|Das Framework wurde bereits eine Zuordnung zur Unterstützung von Ereignissen, Eigenschaften und Methoden, sodass Sie sich auf das konzentrieren, wie die Eigenschaften und Methoden implementiert werden des Steuerelements definiert. Die Standardseite für die Eigenschaft angezeigt werden kann und eine Standardmethode für das Feld über bereitgestellt wird.|
|Erstellen Sie auf der Seite oder Seiten des Steuerelements.|Verwenden Sie die Visual C++-Ressourcen-Editoren, um die visuelle Benutzeroberfläche für die Eigenschaftenseite des Steuerelements bearbeiten:<br /><br /> – Erstellen Sie zusätzliche Eigenschaftenseiten.<br />– Erstellen und Bearbeiten von Bitmaps, Symbole und Cursor.<br /><br /> Sie können auch die Eigenschaftenseiten der Dialog-Editor testen.|Die vom MFC-Anwendungs-Assistenten erstellte Ressourcendatei stellt viele der Ressourcen, die Sie benötigen. Visual C++ können Sie die vorhandene Ressourcen bearbeiten und neue Ressourcen hinzufügen, einfache und visuelle.|
|Testen Sie die Ereignisse, Methoden und Eigenschaften des Steuerelements.|Erstellen Sie das Steuerelement neu ein, und Verwenden von Testcontainer um zu testen, ob die Handler ordnungsgemäß ausgeführt.|Sie können die Methoden des Steuerelements aufrufen und die Eigenschaften, die über die Schnittstelle der Eigenschaftenseite oder Testcontainer bearbeiten. Darüber hinaus können Sie Testcontainer Nachverfolgen von Ereignissen aus dem Steuerelement ausgelöst und Benachrichtigungen, die von der Container des Steuerelements empfangen.|

## <a name="see-also"></a>Siehe auch

[Erstellen im Framework](../mfc/building-on-the-framework.md)<br/>
[Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)

