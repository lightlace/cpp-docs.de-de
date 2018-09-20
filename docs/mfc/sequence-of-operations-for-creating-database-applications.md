---
title: Reihenfolge der Operationen zur Erstellung Datenbankanwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef9c66324f886da27431a94a464554e2a8ddb00a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391571"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Reihenfolge der Operationen zur Erstellung Datenbankanwendungen

Die folgende Tabelle zeigt Ihre Rolle und des Frameworks zum Schreiben von datenbankanwendungen.

> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützen DAO keine (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.

### <a name="creating-database-applications"></a>Erstellen von Datenbankanwendungen

|Aufgabe|Sie tun|Das Framework ermöglicht|
|----------|------------|------------------------|
|Entscheiden Sie, ob die MFC-ODBC oder DAO-Klassen verwenden.|Verwenden von ODBC für neue MFC-Projekte. Verwenden Sie DAO, nur für vorhandene Anwendungen zu verwalten. Weitere Informationen finden Sie im Artikel [Datenzugriffsprogrammierung](../data/data-access-programming-mfc-atl.md).|Das Framework stellt Klassen, die Zugriff auf die Datenbank zu unterstützen.|
|Erstellen Sie Ihre skelettanwendung mit Database-Optionen.|Führen Sie den Assistenten zum MFC-Anwendungen. Wählen Sie Optionen auf der Seite Datenbank-Unterstützung. Wenn Sie eine Option, die eine Datensatzansicht erstellt auswählen, auch Folgendes angeben:<br /><br /> -Data Source "und" Tabelle oder die Namen<br />-Fragen Sie oder die Namen ab.|Der MFC-Anwendung-Assistent erstellt Dateien, und gibt an, dass die erforderlichen enthält. Abhängig von den Optionen, die Sie angeben, können die Dateien eine Recordset-Klasse enthalten.|
|Entwerfen Sie Ihr mindestens ein Datenbankformular.|Verwenden Sie den Visual C++-Dialog-Editor, um Steuerelemente auf die Ressourcen der Dialogfeldvorlage für Ihre Datensatzansichts-Klassen zu platzieren.|Die MFC-Anwendungs-Assistent erstellt eine leere Dialogfeldvorlagen-Ressource für Sie ausgefüllt.|
|Erstellen Sie nach Bedarf zusätzliche aufzeichnen und Recordset-Klassen.|Verwenden Sie Klassenansicht, um die Klassen und das Dialogfeld-Editor, um die Sichten entwerfen, erstellen.|Klassenansicht erstellt zusätzliche Dateien für die neuen Klassen.|
|Erstellen Sie Recordset-Objekte nach Bedarf in Ihrem Code. Verwenden Sie jedes Recordsets Datensätze bearbeiten...|Die Recordsets basieren auf die von abgeleiteten Klassen [CRecordset](../mfc/reference/crecordset-class.md) mit den Assistenten.|ODBC verwendet die Datensatzfeldaustausch (RFX) zum Austauschen von Daten zwischen der Datenbank und des Recordset-Felddatenmembern. Bei Verwendung eine Datensatzansicht Datenaustausch Dialogdatenaustausch (DDX) zwischen dem Recordset und die Steuerelemente der Datensatzansicht angezeigt.|
|... oder erstellen Sie eine explizite [CDatabase](../mfc/reference/cdatabase-class.md) in Ihrem Code für jede Datenbank, die Sie öffnen möchten.|Basieren Sie Ihre Recordset-Objekte, für die Datenbankobjekte.|Das Database-Objekt stellt eine Schnittstelle mit der Datenquelle bereit.|
|Binden von Datenspalten dynamisch an das Recordset.|Fügen Sie Code hinzu abgeleiteten Recordset-Klasse die Bindung zu verwalten, in ODBC. Finden Sie im Artikel [Recordset: Dynamisches Binden von Spalten (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||

## <a name="see-also"></a>Siehe auch

[Erstellen im Framework](../mfc/building-on-the-framework.md)<br/>
[Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[Operationssequenz zur Erstellung von ActiveX-Steuerelementen](../mfc/sequence-of-operations-for-creating-activex-controls.md)
