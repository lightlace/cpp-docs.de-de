---
title: Überschreiben Anbieterdienste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5e54a44be0ad5b7b07311d102871e584770fc441
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571582"
---
# <a name="overriding-provider-service-defaults"></a>Überschreiben der Standardwerte für Anbieterdienste
Der Anbieter Registrierungswert für OLEDB_SERVICES wird zurückgegeben, als der Standardwert für die [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898\(v=vs.85\)) -Eigenschaft zur datenquelleninitialisierung auf das Datenquellenobjekt.  
  
 Solange der Registrierungseintrag vorhanden ist, die Anbieterobjekte werden aggregiert und der Benutzer kann der Anbieter Standardeinstellung für die aktivierten Dienste durch Festlegen von überschreiben die `DBPROP_INIT_OLEDBSERVICES` Eigenschaft vor der Initialisierung. Zum Aktivieren oder deaktivieren einen bestimmten Dienst, den aktuellen Wert der in der Regel von der Benutzer erhält die `DBPROP_INIT_OLEDBSERVICES` -Eigenschaft legt fest oder löscht das Bit für die betreffende Eigenschaft aktiviert bzw. deaktiviert werden soll, und setzt die Eigenschaft zurück. `DBPROP_INIT_OLEDBSERVICES` kann festgelegt werden, direkt in der OLE DB oder in der Verbindungszeichenfolge, die an ADO oder `IDataInitialize::GetDatasource`. Die entsprechenden Werte zum Aktivieren/Deaktivieren einzelner Dienste werden in der folgenden Tabelle aufgeführt.  
  
|Standarddienste, die aktiviert|DBPROP_INIT_OLEDBSERVICES-Eigenschaftswert|Wert in der Verbindungszeichenfolge|  
|------------------------------|------------------------------------------------|--------------------------------|  
|Alle Dienste (Standard)|`DBPROPVAL_OS_ENABLEALL`|"OLE DB-Diensten =-1;"|  
|Alle außer Pooling und AutoEnlistment|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB-Diensten-4; ="|  
|Alle außer den Clientcursor|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB-Diensten-5; ="|  
|Alle außer Pooling AutoEnlistment und Clientcursor|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB-Diensten-7; ="|  
|Keine Dienste|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB-Diensten = 0;"|  
  
 Wenn der Registrierungseintrag für den Anbieter nicht vorhanden ist, die Komponenten-Manager nicht die Anbieterobjekte aggregiert und werden keine Dienste aufgerufen werden, selbst wenn explizit vom Benutzer angefordert.  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcenpooling](/previous-versions/windows/desktop/ms713655\(v=vs.85\))   
 [Verwendung Kunden, die Ressourcenpooling](/previous-versions/windows/desktop/ms715907\(v=vs.85\))   
 [Funktionsweise von Anbietern effektiv mit Ressourcenpooling](/previous-versions/windows/desktop/ms714906\(v=vs.85\))   
 [Aktivieren und Deaktivieren von OLE DB-Diensten](../../data/oledb/enabling-and-disabling-ole-db-services.md)