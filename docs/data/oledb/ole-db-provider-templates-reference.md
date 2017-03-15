---
title: "Referenz der OLE&#160;DB-Anbietervorlagen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbietervorlagen"
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Referenz der OLE&#160;DB-Anbietervorlagen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Klassen und Schnittstellen für die OLE DB\-Anbietervorlagen können in die folgenden Kategorien gruppiert werden.  Das Referenzmaterial enthält auch Informationen über [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md).  
  
 Die Klassen verwenden die folgende Benennungskonvention: Eine Klasse, die mit dem Muster **IWidgetImpl** erstellt haben, müssen eine Implementierung der Schnittstelle **IWidget** bereitgestellt.  
  
## Sitzungs\-Klassen  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 Erstellt eine neue Sitzung vom Datenquellenobjekt und die angeforderte Schnittstelle der neu erstellten Sitzung zurückkehren.  Erforderliche Schnittstelle auf Datenquellenobjekte.  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 Implementiert Sitzungseigenschaften durch Aufrufen einer statischen Funktion definiert durch die Eigenschaftensetzuordnung.  Die Eigenschaftensetzuordnung sollte in der Sitzungsklasse angegeben werden.  Erforderliche Schnittstellen von Sitzungen.  
  
## Rowset\-Klassen  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 Stellt eine Standard\-OLEDB\-Rowsetimplementierung bereit, ohne viele Implementierungsschnittstellen Mehrfachvererbung zu erfordern.  Die einzige Methode, für die Sie die Implementierung bereitstellen müssen, ist **Ausführen**.  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 Stellt eine Standardimplementierung für das Zeilenhandle bereit, das in der `IRowsetImpl`\-Klasse verwendet wird.  Ein Zeilenhandle ist logisch ein eindeutiges Tag für eine Ergebniszeile.  `IRowsetImpl` erstellt einen neuen `CSimpleRow` für jede Zeile, die in `IRowsetImpl::GetNextRows` angefordert wird.  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB benötigt Anbieter, **HACCESSOR** zu implementieren, das einen Tag auf einem Array **DBBINDING**\-Strukturen ist.  Stellt **HACCESSOR**s bereit, das der Adressen **BindType**\-Strukturen sind.  Erforderlich auf Rowsets und Befehlen.  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 Delegaten zu einer statischen Funktion definiert durch die Anbieterspaltenzuordnung.  Erforderliche Schnittstelle auf Rowsets und Befehlen.  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 Gibt Informationen zur Verfügbarkeit von Typkonvertierungen auf einen Befehl oder auf einem Rowset.  Erforderlich auf Befehlen, Rowsets und Indexrowsets.  Implementiert die Schnittstelle **IConvertType**  durch Delegieren zur Konvertierung des Objekts, das von OLE DB angegeben wird.  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 Implementiert die **IDBSchemaRowset**\-Schnittstelle und die auf Vorlagen basierende Erstellerfunktion `CreateSchemaRowset`.  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 Öffnet und gibt ein Rowset zurückgegeben, das sämtliche Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.  Erforderliche Schnittstelle für Sitzungsobjekte.  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 Implementiert die OLE DB\- [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)\-Schnittstelle, die die Aktualisierung der Werte für Spalten in vorhandenen Zeilen aktiviert, Zeilen gelöscht, und neue Zeilen einfügen.  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 Diese Klasse erbt von [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) und überschreibt [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  `IRowsetCreatorImpl` akzeptiert, erfüllt die gleichen Aufgaben wie `IObjectWithSite` können jedoch auch die OLE DB\-Eigenschaften **DBPROPCANSCROLLBACKWARDS** und **DBPROPCANFETCHBACKWARDS**.  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 Implementiert die Schnittstelle **IRowsetIdentity**, die Ihnen ermöglicht, vergleichen, ob zwei Zeilen aus Daten oder nicht identisch sind.  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 Stellt eine Implementierung der Schnittstelle `IRowset` bereit, die die Basisklasse Rowsetschnittstelle ist.  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 Implementiert die Rowseteigenschaften mithilfe der Eigenschaftensetzuordnung, die in der Befehlsklasse definiert wird.  Erforderliche Schnittstelle auf Rowsets.  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 Implementiert die OLE DB\- [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)\-Schnittstelle, die beliebige Zeilen aus einem Rowset abgerufen werden.  Um in OLE DB\-Lesezeichen einem Rowset zu unterstützen, führen Sie das Rowset erben von dieser Klasse.  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 Implementiert übertrugen Features, die Listener am **IID\_IRowsetNotify** \- Verbindungspunkt Inhalt des Rowsets geändert wurde.  Consumer, die Benachrichtigungen bearbeiten, implementieren [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) und registrieren es auf diesem Verbindungspunkt.  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 Implementiert die OLE DB\- [IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)\-Schnittstelle, die Consumern, die Übertragung von verzögerter Aktualisierungen aktiviert, die mit [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) in der Datenquelle und Änderungen vor Übertragung rückgängig machen vorgenommen werden.  
  
## Befehlsklassen  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 Stellt eine Implementierung der `ICommand`\-Schnittstelle bereit.  Diese Schnittstelle wird nicht angezeigt, wird aber durch **ICommandTextImpl** behandelt.  Eine erforderliche Schnittstelle im Befehlsobjekt.  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 Diese Implementierung der Schnittstelle **ICommandProperties** wird von einer statischen Funktion bereitgestellt, die durch das Makro `BEGIN_PROPSET_MAP` definiert wird.  Erforderlich auf Befehlen.  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 Sätze, Speicher und gibt der Befehlstext.  Erforderlich auf Befehlen.  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 Erstellt einen neuen Befehl vom Sitzungsobjekt und die angeforderte Schnittstelle auf dem neu erstellten Befehl zurück.  Optionale Schnittstelle auf Sitzungsobjekten.  
  
 Andere Befehlsklassen sind `IColumnsInfoImpl` und `IAccessorImpl`, das im Rowset\-Klassenabschnitt oben.  
  
## Datenquellen\-Klassen  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 Erstellt und löscht die Verbindung mit dem Consumer.  Erforderliche Schnittstelle auf Datenquellenobjekte und optionale Schnittstelle auf Enumeratoren.  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` ist eine erforderliche Schnittstelle für Datenquellenobjekte und eine optionale Schnittstelle für Enumeratoren.  Wenn ein Enumerator **IDBInitialize** verfügbar macht, muss es `IDBProperties` \(Eigenschaften in der Datenquelle\) verfügbar machen.  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 Erhält einen Schnittstellenzeiger dem Datenquellenobjekt.  Erforderliche Schnittstellen der Sitzung.  
  
## Andere Klassen  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 Implementiert Eigenschaften für eine Reihe von OLE DB\-Eigenschaftenschnittstellen \(beispielsweise, `IDBProperties`, **ISessionProperties** und `IRowsetInfo`\).  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 Implementiert die OLE DB\- [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)\-Schnittstelle, fügt Datensätzen zu hinzu und ruft Datensätze von einem Datenmember ab.  
  
## Siehe auch  
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB\-Vorlagen](../../data/oledb/ole-db-templates.md)