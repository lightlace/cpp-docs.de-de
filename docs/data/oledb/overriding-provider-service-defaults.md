---
title: "&#220;berschreiben der Standardwerte f&#252;r Anbieterdienste | Microsoft Docs"
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
  - "OLE DB-Dienste [OLE DB], Überschreiben des Standard"
  - "Serviceanbieter [OLE DB]"
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# &#220;berschreiben der Standardwerte f&#252;r Anbieterdienste
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Registrierungswert des Anbieters für **OLEDB\_SERVICES** wird als Standardwert für die [DBPROP\_INIT\_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx)\-Initialisierungseigenschaft des Datenquellenobjekts zurückgegeben.  
  
 So lange der Registrierungseintrag besteht, werden die Anbieterobjekte aggregiert, und der Benutzer kann die Anbieterstandardeinstellung für aktivierte Dienste überschreiben, indem er vor der Initialisierung die **DBPROP\_INIT\_OLEDBSERVICES**\-Eigenschaft festlegt.  Um einen bestimmten Dienst zu aktivieren bzw. zu deaktivieren, ruft der Benutzer im Allgemeinen den aktuellen Wert der **DBPROP\_INIT\_OLEDBSERVICES**\-Eigenschaft ab, setzt oder löscht das Bit für die jeweilige zu aktivierende oder zu deaktivierende Eigenschaft und setzt die Eigenschaft zurück.  **DBPROP\_INIT\_OLEDBSERVICES** kann direkt in OLE DB oder in der Verbindungszeichenfolge festgelegt werden, die an ADO oder **IDataInitialize::GetDatasource** übergeben wird.  Die entsprechenden Werte zum Aktivieren\/Deaktivieren einzelner Dienste sind in der folgenden Tabelle aufgelistet.  
  
|Aktivierte Standarddienste|DBPROP\_INIT\_OLEDBSERVICES\-Eigenschaftswert|Wert in Verbindungszeichenfolge|  
|--------------------------------|---------------------------------------------------|-------------------------------------|  
|Alle Dienste \(Standard\)|**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= \-1;"|  
|Alle Dienste außer Pooling und AutoEnlistment|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT**|"OLE DB Services \= \-4;"|  
|Alle Dienste außer Client Cursor|**DBPROPVAL\_OS\_ENABLEALL**&<br /><br /> ~**DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-5;"|  
|Alle Dienste außer Pooling, AutoEnlistment und Client Cursor|**DBPROPVAL\_OS\_ENABLEALL &**<br /><br /> **~DBPROPVAL\_OS\_TXNENLISTMENT &**<br /><br /> **~DBPROPVAL\_OS\_CLIENTCURSOR**|"OLE DB Services \= \-7;"|  
|Keine Dienste|~**DBPROPVAL\_OS\_ENABLEALL**|"OLE DB Services \= 0;"|  
  
 Wenn kein Registrierungseintrag für den Anbieter vorhanden ist, werden die Anbieterobjekte von den Komponenten\-Managern nicht aggregiert, und es werden auch keine Dienste aufgerufen, und zwar auch dann nicht, wenn diese vom Benutzer explizit angefordert wurden.  
  
## Siehe auch  
 [Resource Pooling](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [How Consumers Use Resource Pooling](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [How Providers Work Effectively with Resource Pooling](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [Aktivieren und Deaktivieren von OLE DB\-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)