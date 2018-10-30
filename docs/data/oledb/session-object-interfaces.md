---
title: Sitzungsobjekt-Schnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: cf6f84791e0330c09f61ee612069564781086cc4
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216343"
---
# <a name="session-object-interfaces"></a>Sitzungsobjekt-Schnittstellen

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Objekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721)|Erforderlich|Ja|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946)|Erforderlich|Ja|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721)|Erforderlich|Ja|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943)|Optional|Nein|
|[IAlterTable](/previous-versions/windows/desktop/ms719764)|Optional|Nein|
|[IBindResource](/previous-versions/windows/desktop/ms714936)|Optional|Nein|
|[ICreateRow](/previous-versions/windows/desktop/ms716832)|Optional|Nein|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625)|Optional|Ja|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686)|Optional|Ja|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593)|Optional|Nein|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|Ja|
|[ITableCreation](/previous-versions/windows/desktop/ms713639)|Optional|Nein|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277)|Optional|Nein|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947)|Optional|Nein|
|[ITransaction](/previous-versions/windows/desktop/ms723053)|Optional|Nein|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071)|Optional|Nein|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893)|Optional|Nein|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659)|Optional|Nein|

Das Sitzungsobjekt erstellt ein Rowsetobjekt. Wenn der Anbieter Befehle unterstützt, der die Sitzung auch erstellt ein Command-Objekt (`CCommand`, implementiert der OLE DB `TCommand`). Das Command-Objekt implementiert die `ICommand` -Schnittstelle und verwendet die `ICommand::Execute` Methode zum Ausführen von Befehlen auf das Rowset, wie in der folgenden Abbildung dargestellt.

![Konzeptionelles Diagramm zu Anbietern](../../data/oledb/media/vc4u551.gif "vc4u551")

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
