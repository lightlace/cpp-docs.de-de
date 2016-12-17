---
title: "CMyProviderSession (MyProviderSess.H)"
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
  - "cmyprovidersession"
  - ""myprovidersess.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSession Klasse in MyProviderSess.H"
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: d37ad471-cf05-49c5-aa47-cd10824d777f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSession (MyProviderSess.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**MyProviderSess.H** umfasst die Deklaration und Implementierung für das OLE DB\-Sitzungsobjekt.  Das Datenquellenobjekt erstellt das Sitzungsobjekt und stellt eine Konversation zwischen einem Consumer und einem Anbieter dar.  Für eine Datenquelle können mehrere Sitzungen gleichzeitig geöffnet sein.  Im Folgenden sehen Sie die Vererbungsliste für `CMyProviderSession`:  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSession  
class ATL_NO_VTABLE CMyProviderSession :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public IGetDataSourceImpl<CMyProviderSession>,  
   public IOpenRowsetImpl<CMyProviderSession>,  
   public ISessionPropertiesImpl<CMyProviderSession>,  
   public IObjectWithSiteSessionImpl<CMyProviderSession>,  
   public IDBSchemaRowsetImpl<CMyProviderSession>,  
   public IDBCreateCommandImpl<CMyProviderSession, CMyProviderCommand>  
```  
  
 Das Sitzungsobjekt erbt von **IGetDataSource**, `IOpenRowset`, **ISessionProperties** und **IDBCreateCommand**.  Mithilfe der **IGetDataSource**\-Schnittstelle kann eine Sitzung die Datenquelle abrufen, durch die sie erstellt wurde.  Dieses Feature ist hilfreich, wenn Sie Eigenschaften von der Datenquelle abrufen müssen, die Sie erstellt haben, oder andere Informationen von der Datenquelle benötigen.  Die **ISessionProperties**\-Schnittstelle ist für die Verwaltung sämtlicher Sitzungseigenschaften zuständig.  Die Schnittstellen `IOpenRowset` und **IDBCreateCommand** werden für Datenbankaufgaben verwendet.  Wenn der Anbieter Befehle unterstützt, implementiert er die **IDBCreateCommand**\-Schnittstelle.  Sie wird verwendet, um das zur Ausführung von Befehlen erforderliche Befehlsobjekt zu erstellen.  Das `IOpenRowset`\-Objekt wird immer vom Anbieter implementiert.  Es dient dazu, ein einfaches Rowset von einem Anbieter zu generieren.  Dabei handelt es sich um ein Standardrowset \(z. B. `"select * from mytable"`\) von einem Anbieter.  
  
 Der Assistent generiert zusätzlich drei Sitzungsklassen: `CMyProviderSessionColSchema`, `CMyProviderSessionPTSchema` und `CMyProviderSessionTRSchema`.  Diese Sitzungen werden für Schemarowsets verwendet.  Schemarowsets ermöglichen es dem Anbieter, Metadaten an den Consumer zurückzugeben, ohne dass der Consumer eine Abfrage ausführen oder Daten abrufen muss.  Metadateien abzurufen, ist häufig wesentlich zeitsparender, als die Funktionen eines Anbieters zu identifizieren.  
  
 Laut OLE DB\-Spezifikation müssen Anbieter, die die **IDBSchemaRowset**\-Schnittstelle implementieren, drei Schemarowsettypen unterstützen: **DBSCHEMA\_COLUMNS**, **DBSCHEMA\_PROVIDER\_TYPES** und `DBSCHEMA_TABLES`.  Implementierungen für die einzelnen Schemarowsets werden vom Assistenten generiert.  Jede vom Assistenten generierte Klasse verfügt über eine `Execute`\-Methode.  In dieser `Execute`\-Methode können an den Anbieter Informationen zu unterstützten Tabellen, Spalten und Datentypen zurückgegeben werden.  Diese Daten sind in der Regel zur Kompilierungszeit bekannt.  
  
## Siehe auch  
 [Vom Anbieter\-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)