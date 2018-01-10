---
title: Referenz der OLE DB-Anbieter Vorlagen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.templates.ole
dev_langs: C++
helpviewer_keywords: OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a68c3f0b161a21749ad49b1b89a1356b757d4b76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ole-db-provider-templates-reference"></a>Referenz der OLE DB-Anbietervorlagen
Die Klassen und Schnittstellen für OLE DB-Anbietervorlagen können in folgenden Kategorien gruppiert werden. Das Referenzmaterial enthält auch Informationen zu den [Makros für OLE DB-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Die Klassen verwenden die folgende Benennungskonvention: eine Klasse mit dem Muster namens **IWidgetImpl** würde eine Implementierung der Schnittstelle bereitstellen **IWidget**.  
  
## <a name="session-classes"></a>Sitzungsklassen  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Erstellt eine neue Sitzung aus dem Datenquellensicht-Objekt und gibt die angeforderte Schnittstelle auf die neu erstellte Sitzung zurück. Verbindliche Schnittstelle für Datenquellenobjekte.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Implementiert die Sitzungseigenschaften durch den Aufruf einer statischen Funktion, die von der Eigenschaft Satz Zuordnung definiert. Die Satz eigenschaftenzuordnung sollte in Ihrer Sitzungsklasse angegeben werden. Verbindliche Schnittstelle für Sitzungen.  
  
## <a name="rowset-classes"></a>Schemarowset-Klassen  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Stellt eine Standardimplementierung der OLE DB-Rowset ohne mehrfache Vererbung von vielen Implementierung Schnittstellen bereit. Die einzige Methode, die für die Sie bereitstellen müssen, Implementierung **Execute**.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Stellt eine Standardimplementierung für das Zeilenhandle, im dient der `IRowsetImpl` Klasse. Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile. `IRowsetImpl`erstellt ein neues `CSimpleRow` für jede Zeile im angeforderten `IRowsetImpl::GetNextRows`.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB benötigt Anbietern zum Implementieren einer **HACCESSOR**, dies ist ein Tag auf ein Array von **DBBINDING** Strukturen. Bietet **HACCESSOR**e, die Adressen der sind die **BindType** Strukturen. Erforderlich für Rowsets und Befehle.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Delegaten an eine statische Funktion, die von der Spalte-Zuordnung von Anbieter definiert. Verbindliche Schnittstelle für Rowsets und Befehle.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Erhalten Informationen über die Verfügbarkeit von typkonvertierungen aus, auf einen Befehl oder für ein Rowset. Obligatorisch auf Befehle, Rowsets und Index-Rowsets. Implementiert die **IConvertType** delegieren, auf das Konvertierungsobjekt vom OLE DB-Schnittstelle.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Implementiert die **IDBSchemaRowset** Schnittstelle und die vorlagenbasierte erstellerfunktion `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält. Verbindliche Schnittstelle für ein Sitzungsobjekt.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Implementiert die OLE DB- [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) -Schnittstelle, die Aktualisieren der Werte der Spalten in vorhandenen Zeilen löschen von Zeilen, und neue Zeilen einfügen kann.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Diese Klasse erbt von ["IObjectWithSite"](http://msdn.microsoft.com/library/windows/desktop/ms693765) und überschreibt [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). `IRowsetCreatorImpl`führt die gleichen Funktionen wie `IObjectWithSite` können jedoch auch die Eigenschaften des OLE DB- **DBPROPCANSCROLLBACKWARDS** und **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Implementiert die **IRowsetIdentity** -Schnittstelle, die können Sie vergleichen, ob zwei Zeilen mit Daten identisch sind.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 Stellt eine Implementierung von der `IRowset` -Schnittstelle, die die grundlegende Rowset-Schnittstelle ist.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Implementiert die Rowseteigenschaften mit der Eigenschaft legen Sie in Ihre Befehlsklasse definierte Zuordnung. Verbindliche Schnittstelle für Rowsets.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Implementiert die OLE DB- [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx) -Schnittstelle, die beliebige Zeilen aus einem Rowset abruft. Stellen Sie zur Unterstützung von OLE DB-Lesezeichen in einem Rowset, das Rowset, das von dieser Klasse erben.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Implementiert broadcast Funktionen zum Listener über dem Verbindungspunkt beraten **IID_IRowsetNotify** Änderungen an den Inhalt des Rowsets. Implementieren von Consumern, die Benachrichtigungen behandeln [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) und registrieren Sie ihn auf diese Verbindung an.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 Implementiert die OLE DB- [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx) -Schnittstelle, die Consumer die Übertragung von Änderungen durch verzögert ermöglicht [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) auf die Datenquelle und vor der Übertragung Änderungen rückgängig zu machen.  
  
## <a name="command-classes"></a>Befehlsklassen  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 Stellt eine Implementierung der `ICommand`-Schnittstelle bereit. Diese Schnittstelle ist nicht sichtbar, aber erfolgt durch **ICommandTextImpl**. Keine verbindliche Schnittstelle für das Command-Objekt.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Diese Implementierung der **ICommandProperties** Schnittstelle erfolgt über eine statische Funktion definiert, indem die `BEGIN_PROPSET_MAP` Makro. Obligatorisch einschaltbefehle.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Legt fest, speichert, und gibt den Befehlstext. Obligatorisch einschaltbefehle.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Erstellt einen neuen Befehl über das Sitzungsobjekt und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Befehl. Eine optionale Schnittstelle für Session-Objekte.  
  
 Sind andere Befehlsklassen `IColumnsInfoImpl` und `IAccessorImpl`, der im obigen Abschnitt zu Schemarowset-Klassen beschrieben.  
  
## <a name="data-source-classes"></a>Datenquellenklassen  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 Erstellt und löscht die Verbindung mit dem Consumer. Verbindliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle auf Enumeratoren.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties`ist keine verbindliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren. Jedoch, wenn Sie einen Enumerator verfügbar macht **IDBInitialize**, verfügbar machen `IDBProperties` (Eigenschaften für die Datenquelle).  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Ruft einen Schnittstellenzeiger auf das Datenquellenobjekt ab. Verbindliche Schnittstelle für die Sitzung.  
  
## <a name="other-classes"></a>Andere Klassen  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Eigenschaften für eine Vielzahl von OLE DB-Schnittstellen implementiert (z. B. `IDBProperties`, **ISessionProperties**, und `IRowsetInfo`).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Implementiert die OLE DB- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) -Schnittstelle, Hinzufügen von Datensätzen an und Abrufen von Datensätzen aus einem Datenelement.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB-Vorlagen](../../data/oledb/ole-db-templates.md)