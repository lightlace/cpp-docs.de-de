---
title: Sitzungsobjekt-Schnittstellen
ms.date: 10/24/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 19a2830ba97038624072ce4d9b8eca573ddd7d28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588720"
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
