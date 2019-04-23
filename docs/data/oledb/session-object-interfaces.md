---
title: Sitzungsobjekt-Schnittstellen
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: 2fb91365fec0709e1bb2a26afa519e6565862681
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031448"
---
# <a name="session-object-interfaces"></a>Sitzungsobjekt-Schnittstellen

Die folgende Tabelle zeigt die erforderlichen und optionalen Schnittstellen, die durch OLE DB für ein Objekt definiert.

|Interface|Erforderlich?|Vom OLE DB-Vorlagen implementiert?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Erforderlich|Ja|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Erforderlich|Ja|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Erforderlich|Ja|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|Optional|Nein|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|Optional|Nein|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|Optional|Nein|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|Optional|Nein|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|Optional|Ja|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|Optional|Ja|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|Optional|Nein|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|Ja|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|Optional|Nein|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|Optional|Nein|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|Optional|Nein|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|Optional|Nein|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|Optional|Nein|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|Optional|Nein|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|Optional|Nein|

Das Sitzungsobjekt erstellt ein Rowsetobjekt. Wenn der Anbieter Befehle unterstützt, der die Sitzung auch erstellt ein Command-Objekt (`CCommand`, implementiert der OLE DB `TCommand`). Das Command-Objekt implementiert die `ICommand` -Schnittstelle und verwendet die `ICommand::Execute` Methode zum Ausführen von Befehlen auf das Rowset, wie in der folgenden Abbildung dargestellt.

![Konzeptionelles Diagramm zu Anbietern](../../data/oledb/media/vc4u551.gif "konzeptionelles Diagramm zu Anbietern")

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
