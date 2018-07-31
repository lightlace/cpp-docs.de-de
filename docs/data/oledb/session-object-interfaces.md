---
title: Sitzungsobjekt-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 01d08fb35a1e954aad07153f63ad3ed34282570d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337845"
---
# <a name="session-object-interfaces"></a>Sitzungsobjekt-Schnittstellen
Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Objekt definiert.  
  
|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx)|Erforderlich|Ja|  
|[IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx)|Erforderlich|Ja|  
|[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)|Erforderlich|Ja|  
|[IAlterIndex](https://msdn.microsoft.com/library/ms714943.aspx)|Optional|Nein|  
|[IAlterTable](https://msdn.microsoft.com/library/ms719764.aspx)|Optional|Nein|  
|[IBindResource](https://msdn.microsoft.com/library/ms714936.aspx)|Optional|Nein|  
|[ICreateRow](https://msdn.microsoft.com/library/ms716832.aspx)|Optional|Nein|  
|[IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx)|Optional|Ja|  
|[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)|Optional|Ja|  
|[IIndexDefinition](https://msdn.microsoft.com/library/ms711593.aspx)|Optional|Nein|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|Ja|  
|[ITableCreation](https://msdn.microsoft.com/library/ms713639.aspx)|Optional|Nein|  
|[ITableDefinition](https://msdn.microsoft.com/library/ms714277.aspx)|Optional|Nein|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/library/ms720947.aspx)|Optional|Nein|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|Optional|Nein|  
|[ITransactionJoin](https://msdn.microsoft.com/library/ms718071.aspx)|Optional|Nein|  
|[ITransactionLocal](https://msdn.microsoft.com/library/ms714893.aspx)|Optional|Nein|  
|[ITransactionObject](https://msdn.microsoft.com/library/ms713659.aspx)|Optional|Nein|  
  
 Das Sitzungsobjekt erstellt ein Rowsetobjekt. Wenn der Anbieter Befehle unterstützt, der die Sitzung auch erstellt ein Command-Objekt (`CCommand`, implementiert der OLE DB `TCommand`). Das Command-Objekt implementiert die `ICommand` -Schnittstelle und verwendet die `ICommand::Execute` Methode zum Ausführen von Befehlen auf das Rowset, wie in der folgenden Abbildung dargestellt.  
  
 ![Konzeptionelles Diagramm zu Anbietern](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)