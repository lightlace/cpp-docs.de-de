---
title: "CMyProviderSource (MyProviderDS.H)"
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
  - ""myproviderds.h""
  - "cmyprovidersource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSource Klasse in MyProviderDS.H"
  - "OLE DB-Anbieter, Assistentengenerierte Dateien"
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSource (MyProviderDS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Anbieterklassen verwenden die Mehrfachvererbung.  Der folgende Code veranschaulicht die Vererbungskette für das Datenquellenobjekt:  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 Alle COM\-Komponenten werden von `CComObjectRootEx` und `CComCoClass` abgeleitet.  `CComObjectRootEx` stellt die gesamte Implementierung für die **IUnknown**\-Schnittstelle bereit.  Jedes Threadingmodell kann behandelt werden.  `CComCoClass` behandelt jede erforderliche Fehlerunterstützung.  Wenn ausführlichere Fehlerinformationen an den Client gesendet werden sollen, können Sie einige der Fehler\-APIs in `CComCoClass` verwenden.  
  
 Zusätzlich erbt das Datenquellenobjekt von mehreren "Impl"\-Klassen.  Jede Klasse stellt die Implementierung für eine Schnittstelle bereit.  Das Datenquellenobjekt implementiert die Schnittstellen `IPersist`, `IDBProperties`, **IDBInitialize** und **IDBCreateSession**.  Zur Implementierung des Datenquellenobjekts benötigt OLE DB jede dieser Schnittstellen.  Es können bestimmte Funktionen unterstützt werden, je nachdem, ob Sie die Vererbung von einer dieser "Impl"\-Klassen zulassen oder nicht.  Wenn die **IDBDataSourceAdmin**\-Schnittstelle unterstützt werden soll, müsste die Vererbung von der **IDBDataSourceAdminImpl**\-Klasse möglich sein, damit die erforderlichen Funktionen bereitgestellt werden können.  
  
## COM\-Zuordnung  
 Sobald der Client `QueryInterface` für eine Schnittstelle der Datenquelle aufruft, durchläuft er die folgende COM\-Zuordnung:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 Die **COM\_INTERFACE\_ENTRY**\-Makros sind Bestandteil von ATL und weisen die Implementierung von `QueryInterface` in `CComObjectRootEx` an, die geeigneten Schnittstellen zurückzugeben.  
  
## Eigenschaftenzuordnung  
 In der Eigenschaftenzuordnung sind alle vom Anbieter bezeichneten Eigenschaften aufgeführt:  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)  
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)  
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)  
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)  
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)  
      PROPERTY_INFO_ENTRY(CATALOGTERM)  
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)  
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)  
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)  
      PROPERTY_INFO_ENTRY(DATASOURCENAME)  
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)  
      PROPERTY_INFO_ENTRY(DBMSNAME)  
      PROPERTY_INFO_ENTRY(DBMSVER)  
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)  
      PROPERTY_INFO_ENTRY(GROUPBY)  
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)  
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)  
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)  
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)  
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)  
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)  
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)  
      PROPERTY_INFO_ENTRY(NULLCOLLATION)  
      PROPERTY_INFO_ENTRY(OLEOBJECTS)  
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)  
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)  
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)  
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PROCEDURETERM)  
      PROPERTY_INFO_ENTRY(PROVIDERNAME)  
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)  
      PROPERTY_INFO_ENTRY(PROVIDERVER)  
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)  
      PROPERTY_INFO_ENTRY(SCHEMATERM)  
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)  
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)  
      PROPERTY_INFO_ENTRY(SUBQUERIES)  
      PROPERTY_INFO_ENTRY(TABLETERM)  
      PROPERTY_INFO_ENTRY(USERNAME)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)  
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)  
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)  
      PROPERTY_INFO_ENTRY(AUTH_USERID)  
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)  
      PROPERTY_INFO_ENTRY(INIT_HWND)  
      PROPERTY_INFO_ENTRY(INIT_LCID)  
      PROPERTY_INFO_ENTRY(INIT_LOCATION)  
      PROPERTY_INFO_ENTRY(INIT_MODE)  
      PROPERTY_INFO_ENTRY(INIT_PROMPT)  
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)  
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)  
   END_PROPERTY_SET(DBPROPSET_DBINIT)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)  
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)  
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 Eigenschaften in OLE DB sind gruppiert.  Das Datenquellenobjekt verfügt über zwei Eigenschaftengruppen: eine für das **DBPROPSET\_DATASOURCEINFO**\-Set und eine für das **DBPROPSET\_DBINIT**\-Set.  Das **DBPROPSET\_DATASOURCEINFO**\-Set entspricht den Eigenschaften des Anbieters und seiner Datenquelle.  Das **DBPROPSET\_DBINIT**\-Set entspricht den bei der Initialisierung verwendeten Eigenschaften.  Die OLE DB\-Anbietervorlagen verwalten diese Sets mithilfe der **PROPERTY\_SET**\-Makros.  Durch die Makros wird ein Block erstellt, der ein Eigenschaftenarray enthält.  Wann immer der Client die `IDBProperties`\-Schnittstelle aufruft, verwendet der Anbieter die Eigenschaftenzuordnung.  
  
 Sie brauchen nicht jede Eigenschaft in der Spezifikation zu implementieren.  Die erforderlichen Eigenschaften müssen jedoch unterstützt werden. Weitere Informationen finden Sie in der Spezifikation zur Level 0\-Konformität.  Falls eine Eigenschaft nicht unterstützt werden soll, entfernen Sie sie aus der Zuordnung.  Soll eine Eigenschaft unterstützt werden, fügen Sie sie der Zuordnung mithilfe eines PROPERTY\_INFO\_ENTRY\-Makros hinzu.  Das Makro entspricht der im folgenden Code dargestellten **UPROPINFO**\-Struktur:  
  
```  
struct UPROPINFO  
{  
   DBPROPID    dwPropId;  
   ULONG       ulIDS;  
   VARTYPE     VarType;  
   DBPROPFLAGS dwFlags;  
   union  
   {  
      DWORD dwVal;  
      LPOLESTR szVal;  
   };  
   DBPROPOPTIONS dwOption;  
};  
```  
  
 Jedes Element in der Struktur enthält Informationen zur Behandlung der Eigenschaft.  Es enthält eine **DBPROPID**, um die GUID und ID für die Eigenschaft zu bestimmen.  Außerdem sind Einträge zur Bestimmung des Eigenschaftentyps und \-werts vorhanden.  
  
 Wenn Sie den Standardwert einer Eigenschaft ändern möchten \(beachten Sie, dass der Wert einer aktualisierbaren Eigenschaft jederzeit von einem Consumer geändert werden kann\), können Sie entweder das Makro PROPERTY\_INFO\_ENTRY\_VALUE oder das Makro PROPERTY\_INFO\_ENTRY\_EX verwenden.  Diese Makros bieten die Möglichkeit, einen Wert für eine entsprechende Eigenschaft anzugeben.  Das **PROPERTY\_INFO\_ENTRY\_VALUE**\-Makro ist eine Kurznotation, mit der Sie den Wert ändern können.  Durch das **PROPERTY\_INFO\_ENTRY\_VALUE**\-Makro wird das **PROPERTY\_INFO\_ENTRY\_EX**\-Makro aufgerufen.  Mithilfe dieses Makros können Sie sämtliche Attribute in der **UPROPINFO**\-Struktur hinzufügen oder ändern.  
  
 Wenn Sie ein eigenes Eigenschaftenset definieren möchten, können Sie ein Set durch eine zusätzliche BEGIN\_PROPSET\_MAP\/END\_PROPSET\_MAP\-Kombination hinzufügen.  Zunächst müssen Sie eine GUID für das Eigenschaftenset und anschließend eigene Eigenschaften definieren.  Anbieterspezifische Eigenschaften sollten einem neuen und keinem bestehenden Eigenschaftenset hinzugefügt werden.  Auf diese Weise werden Probleme mit späteren OLE DB\-Versionen vermieden.  
  
## Benutzerdefinierte Eigenschaftensets  
 Visual C\+\+ .NET unterstützt benutzerdefinierte Eigenschaftensets.  Folglich müssen **GetProperties** oder `GetPropertyInfo` nicht mehr überschrieben werden.  Die Vorlagen sind stattdessen in der Lage, jedes benutzerdefinierte Eigenschaftenset zu erkennen und es dem geeigneten Objekt hinzuzufügen.  
  
 Bei einem benutzerdefinierten Eigenschaftenset, das zur Initialisierungszeit verfügbar sein muss \(d. h., bevor **IDBInitialize::Initialize** vom Consumer aufgerufen wird\), können Sie dieses Merkmal definieren, indem Sie das **UPROPSET\_USERINIT**\-Flag in Verbindung mit dem BEGIN\_PROPERTY\_SET\_EX\-Makro verwenden.  Damit dieser Vorgang erfolgreich verläuft, muss das Eigenschaftenset \(gemäß OLE DB\-Spezifikation\) im Datenquellenobjekt enthalten sein.  Beispiel:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## Siehe auch  
 [Vom Anbieter\-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)