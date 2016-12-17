---
title: "CRowset::Insert"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.Insert"
  - "CRowset.Insert"
  - "CRowset<TAccessor>.Insert"
  - "CRowset<TAccessor>::Insert"
  - "ATL::CRowset<TAccessor>::Insert"
  - "ATL.CRowset.Insert"
  - "CRowset::Insert"
  - "ATL::CRowset::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Insert-Methode"
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Insert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt und initialisiert eine neue Zeile unter Verwendung von Daten aus dem Accessor.  
  
## Syntax  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### Parameter  
 `nAccessor`  
 \[in\] Die Anzahl der für das Einfügen verwenden Accessor, der Daten.  
  
 *bGetHRow*  
 \[in\] gibt an, dass das Handle für die eingefügte Zeile abgerufen wird.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erfordert die optionale `IRowsetChange`\- Schnittstelle, die möglicherweise nicht auf alle Anbieter unterstützt wird; Wenn dies der Fall ist, gibt die Methode **E\_NOINTERFACE** zurück.  Sie müssen **DBPROP\_IRowsetChange** auf `VARIANT_TRUE` festlegen, bevor Sie auf dem Tisch **Öffnen** aufrufen oder den Befehl, das Rowset enthalten.  
  
 EINFG könnte fehlschlagen, wenn eine oder mehrere Spalten nicht möglich ist.  Ändern Sie die Cursorzuordnung, um diesen Fehler zu beheben.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie auf eine Datenquelle von einem Rowset zugreift und dann eine Zeichenfolge mit einer Tabelle in diesem Rowset einfügen.  
  
 Erstellen Sie zunächst eine Tabellenklasse, indem Sie ein neues ATL\-Objekt in Ihr Projekt einfügen.  Klicken Sie beispielsweise auf das Projekt im Arbeitsbereich mit der rechten Maustaste und wählen **Neues ATL\-Objekt** aus.  In der **Datenzugriff** Kategorie die Option **Consumer** aus.  Erstellen Sie ein Consumerobjekt des Typs **Tabelle**. \( **Tabelle** auswählen, erstellt ein Rowset direkt der Tabelle; **Befehl** auswählen, erstellt ein Rowset durch einen SQL\-Befehl.\) Wählen Sie eine Datenquelle aus und angeben mit einer Tabelle, um auf diese Datenquelle zuzugreifen.  Wenn Sie das Consumerobjekt **CCustomerTable** aufrufen, können Sie den Einfügungscode implementieren, wie folgt:  
  
 [!CODE [NVC_OLEDB_Consumer#10](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#10)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)