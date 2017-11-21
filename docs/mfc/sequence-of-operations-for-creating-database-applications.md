---
title: Reihenfolge der Operationen zur Erstellung Datenbankanwendungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 58939d60401af9061288fa5a9b61c25b6278aec8
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2017
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>Reihenfolge der Operationen zur Erstellung Datenbankanwendungen
Die folgende Tabelle zeigt Ihre Rolle und das Framework zum Schreiben von datenbankanwendungen.  
  
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützt nicht DAO (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von ODBC für neue MFC-Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
### <a name="creating-database-applications"></a>Erstellen von Datenbankanwendungen  
  
|Aufgabe|Sie tun|Das Framework ermöglicht|  
|----------|------------|------------------------|  
|Entscheiden Sie, ob die MFC ODBC- oder DAO-Klassen verwenden.|Verwenden von ODBC für neue MFC-Projekte. Verwenden Sie DAO nur für vorhandene Anwendungen zu verwalten. Allgemeine Informationen finden Sie im Artikel [Datenprogrammierung Zugriff](../data/data-access-programming-mfc-atl.md).|Das Framework stellt Klassen, die Zugriff auf die Datenbank zu unterstützen.|  
|Erstellen Sie Ihre skelettanwendung mit Datenbankoptionen an.|Führen Sie den MFC-Anwendung-Assistenten. Wählen Sie Optionen auf der Seite Datenbank-Unterstützung. Wenn Sie eine Option, die eine Datensatzansicht erstellt auswählen, auch Folgendes angeben:<br /><br /> -Daten Quelle und die Tabelle oder die Namen<br />-Fragen Sie oder die Namen ab.|Die MFC-Anwendung-Assistent erstellt Dateien, und gibt an, dass die erforderlichen enthält. Abhängig von den Optionen, die Sie angeben, zählen die Dateien eine Recordset-Klasse.|  
|Entwerfen Sie Ihre Datenbank bilden oder Formulare.|Verwenden Sie den Visual C++-Dialog-Editor, um Steuerelemente auf die Ressourcen der Dialogfeldvorlage für Datensatzansichts-Klassen platzieren.|Die MFC-Anwendungs-Assistent erstellt eine leeres Dialogfeldvorlagen-Ressource für Sie ausgefüllt.|  
|Erstellen Sie nach Bedarf zusätzliche Benutzerdatensatz und Recordset-Klasse.|Verwenden Sie Klassenansicht, um die Klassen und das Dialogfeld-Editor, um die Sichten entwerfen, erstellen.|Klassenansicht erstellt zusätzliche Dateien für die neuen Klassen.|  
|Erstellen Sie Recordset-Objekte nach Bedarf in Ihrem Code. Verwenden Sie jedes Recordset, um Datensätze bearbeiten...|Die Recordsets basieren auf den von abgeleiteten Klassen [CRecordset](../mfc/reference/crecordset-class.md) mit den Assistenten.|Verwendung von ODBC-Datensatzfeldaustausch (RFX) zum Austauschen von Daten zwischen der Datenbank und das Recordset-Felddatenmember. Bei Verwendung eine Datensatzansicht tauscht Dialogdatenaustausch (DDX) Daten zwischen das Recordset und den Steuerelementen der Datensatzansicht angezeigt.|  
|.. oder erstellen Sie eine explizite [CDatabase](../mfc/reference/cdatabase-class.md) in Ihrem Code für jede Datenbank, die Sie öffnen möchten.|Recordset-Objekte als Grundlage für die Datenbankobjekte.|Das Datenbankobjekt stellt eine Schnittstelle mit der Datenquelle.|  
|Binden von Datenspalten dynamisch an das Recordset.|Fügen Sie in ODBC Code zur abgeleiteten Recordsetklasse zum Verwalten von der Bindungsnamens. Finden Sie im Artikel [Recordset: Dynamisches Binden von Spalten (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Reihenfolge der Operationen zur Erstellung von OLE-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Operationssequenz zur Erstellung von ActiveX-Steuerelementen](../mfc/sequence-of-operations-for-creating-activex-controls.md)
