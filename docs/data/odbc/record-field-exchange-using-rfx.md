---
title: "Datensatzfeldaustausch: Verwenden von RFX | Microsoft Docs"
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
  - "RFX (ODBC), Implementieren"
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Datensatzfeldaustausch: Verwenden von RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, was Sie tun müssen, um RFX zu verwenden, und welche Rolle das Framework dabei spielt.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von [CRecordset](../../mfc/reference/crecordset-class.md) abgeleitete Klassen, in denen der gesammelte Zeilenabruf nicht implementiert wurde.  Beim gesammelten Abrufen von Zeilen wird der Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) implementiert.  Der Bulk\-RFX ist mit RFX vergleichbar.  Unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) werden die Unterschiede erläutert.  
  
 Die folgenden Themen enthalten verwandte Informationen:  
  
-   [Datensatzfeldaustausch: Arbeiten mit Assistenten\-Code](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) enthält eine Einführung in die Hauptkomponenten von RFX sowie eine Erläuterung des Codes, den der MFC\-Anwendungs\-Assistent und **Klasse hinzufügen** \(wie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) beschrieben\) zur Unterstützung von RFX erstellen, und erläutert, wie der Assistentencode geändert werden kann.  
  
-   [Datensatzfeldaustausch: Verwenden der RFX\-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) erläutert, wie Sie in der überschriebenen `DoFieldExchange`\-Version RFX\-Funktionen aufrufen.  
  
 Die folgende Tabelle zeigt, welche Aufgaben von Ihnen durchgeführt werden müssen und welche vom Framework durchgeführt werden.  
  
### Verwenden von RFX: Interaktion mit dem Framework  
  
|Benutzer|Framework|  
|--------------|---------------|  
|Sie deklarieren die Recordset\-Klassen mit einem Assistenten.  Sie geben die Namen und Datentypen der Felddatenmember an.|Der Assistent leitet eine `CRecordset`\-Klasse ab und fügt eine überschriebene Version von [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) ein, die für jeden Felddatenmember einen RFX\-Funktionsaufruf enthält.|  
|\(Optional\) Sie fügen der Klasse manuell die benötigten Parameterdatenmember hinzu.  Sie fügen manuell für jeden Parameterdatenmember einen RFX\-Funktionsaufruf für `DoFieldExchange` und für die Parametergruppe einen Aufruf für [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) hinzu. Geben Sie danach die Gesamtzahl der Parameter in [m\_nParams](../Topic/CRecordset::m_nParams.md) an.  Siehe [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||  
|\(Optional\) Sie binden von Hand zusätzliche Spalten an Felddatenmember.  Sie erhöhen [m\_nFields](../Topic/CRecordset::m_nFields.md) manuell.  Siehe [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
|Sie erstellen ein Objekt der Recordset\-Klasse.  Bevor Sie das Objekt verwenden, stellen Sie bei Bedarf die Werte der zugehörigen Parameterdatenmember ein.|Aus Effizienzgründen führt das Framework mithilfe von ODBC eine Vorbindung der Parameter durch.  Wenn Sie Parameterwerte übergeben, gibt das Framework diese an die Datenquelle weiter.  Bei Neuabfragen sendet das Framework lediglich die Parameterwerte, es sei denn, die Sortier\- und\/oder Filterzeichenfolgen hätten sich geändert.|  
|Sie öffnen ein Recordset\-Objekt mit [CRecordset::Open](../Topic/CRecordset::Open.md).|Das Framework führt die Abfrage des Recordsets aus, bindet Spalten an Felddatenmember des Recordsets und ruft `DoFieldExchange` auf, um Daten zwischen dem ersten ausgewählten Datensatz und den Felddatenmembern des Recordsets zu übertragen.|  
|Sie scrollen durch das Recordset mit [CRecordset::Move](../Topic/CRecordset::Move.md) oder über einen Menü\- oder Symbolleistenbefehl.|Ruft `DoFieldExchange` auf, um Daten aus dem neuen aktuellen Datensatz in die Felddatenmember zu übertragen.|  
|Fügt Datensätze hinzu, aktualisiert oder löscht diese.|Das Framework ruft `DoFieldExchange` auf, um Daten zur Datenquelle zu übertragen.|  
  
## Siehe auch  
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Recordset: Abrufen von Summen und anderen Aggregatergebnissen \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [Makros, globale Funktionen und globale Variablen](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)