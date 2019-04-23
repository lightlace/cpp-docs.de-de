---
title: CCustomSource (CustomDS.H)
ms.date: 10/22/2018
f1_keywords:
- myproviderds.h
- cmyprovidersource
- customds.h
- ccustomsource
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
- CCustomSource class in CustomDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
ms.openlocfilehash: 296e7848b1d756fe0aba6156be2501db45bb092b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028599"
---
# <a name="ccustomsource-customdsh"></a>CCustomSource (CustomDS.h)

Die-Anbieterklassen verwenden mehrfache Vererbung. Der folgende Code zeigt die Vererbungskette für das neue Datenquellenobjekt:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource :
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

Leiten Sie alle COM-Komponenten von `CComObjectRootEx` und `CComCoClass`. `CComObjectRootEx` Stellt die Implementierung für die für die `IUnknown` Schnittstelle. Sie können alle threading-Modell behandeln. `CComCoClass` behandelt alle Fehler Unterstützung erforderlich. Wenn Sie ausführlichere Fehlerinformationen an den Client senden möchten, können Sie einige der Fehler-APIs in `CComCoClass`.

Das Datenquellenobjekt erbt auch von mehreren "Impl"-Klassen. Jede Klasse stellt die Implementierung für eine Schnittstelle bereit. Das Datenquellenobjekt implementiert die `IPersist`, `IDBProperties`, `IDBInitialize`, und `IDBCreateSession` Schnittstellen. Jede Schnittstelle ist durch OLE DB erforderlich, um das Datenquellenobjekt zu implementieren. Sie können auch unterstützt, oder bestimmte Funktionen durch Vererbung oder erben nicht von einer dieser Klassen "Impl" unterstützt. Wenn Sie unterstützen möchten die `IDBDataSourceAdmin` -Schnittstelle, erben von der `IDBDataSourceAdminImpl` Klasse, um die erforderliche Funktionalität zu erhalten.

## <a name="com-map"></a>COM-Zuordnung

Jedes Mal, wenn der Client ruft `QueryInterface` für eine Schnittstelle für die Datenquelle, durchläuft sie die folgenden COM-Zuordnung:

```cpp
/////////////////////////////////////////////////////////////////////////
// CCustomSource
class ATL_NO_VTABLE CCustomSource : 
   public CComObjectRootEx<CComSingleThreadModel>,
   public CComCoClass<CCustomSource, &CLSID_Custom>,
   public IDBCreateSessionImpl<CCustomSource, CCustomSession>,
   public IDBInitializeImpl<CCustomSource>,
   public IDBPropertiesImpl<CCustomSource>,
   public IPersistImpl<CCustomSource>,
   public IInternalConnectionImpl<CCustomSource>
```

Leiten Sie alle COM-Komponenten von `CComObjectRootEx` und `CComCoClass`. `CComObjectRootEx` Stellt die Implementierung für die für die `IUnknown` Schnittstelle. Sie können alle threading-Modell behandeln. `CComCoClass` behandelt alle Fehler Unterstützung erforderlich. Wenn Sie ausführlichere Fehlerinformationen an den Client senden möchten, können Sie einige der Fehler-APIs in `CComCoClass`.

Das Datenquellenobjekt erbt auch von mehreren "Impl"-Klassen. Jede Klasse stellt die Implementierung für eine Schnittstelle bereit. Das Datenquellenobjekt implementiert die `IPersist`, `IDBProperties`, `IDBInitialize`, und `IDBCreateSession` Schnittstellen. Jede Schnittstelle ist durch OLE DB erforderlich, um das Datenquellenobjekt zu implementieren. Sie können auch unterstützt, oder bestimmte Funktionen durch Vererbung oder erben nicht von einer dieser Klassen "Impl" unterstützt. Wenn Sie unterstützen möchten die `IDBDataSourceAdmin` -Schnittstelle, erben von der `IDBDataSourceAdminImpl` Klasse, um die erforderliche Funktionalität zu erhalten.

## <a name="com-map"></a>COM-Zuordnung

Jedes Mal, wenn der Client ruft `QueryInterface` für eine Schnittstelle für die Datenquelle, durchläuft sie die folgenden COM-Zuordnung:

```cpp
BEGIN_COM_MAP(CCustomSource)
   COM_INTERFACE_ENTRY(IDBCreateSession)
   COM_INTERFACE_ENTRY(IDBInitialize)
   COM_INTERFACE_ENTRY(IDBProperties)
   COM_INTERFACE_ENTRY(IPersist)
   COM_INTERFACE_ENTRY(IInternalConnection)
END_COM_MAP()
```

Die COM_INTERFACE_ENTRY-Makros sind von ATL und weisen die Implementierung von `QueryInterface` in `CComObjectRootEx` die entsprechenden Schnittstellen zurückgegeben.

## <a name="property-map"></a>Eigenschaftenzuordnung

Die eigenschaftenzuordnung gibt alle vom Anbieter zugewiesenen Eigenschaften an:

```cpp
BEGIN_PROPSET_MAP(CCustomSource)
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
   CHAIN_PROPERTY_SET(CCustomSession)
END_PROPSET_MAP()
```

Eigenschaften in der OLE DB werden gruppiert. Das Objekt verfügt über zwei Gruppen von Eigenschaften: eine für das DBPROPSET_DATASOURCEINFO festgelegt und eine für das DBPROPSET_DBINIT festgelegt. Die DBPROPSET_DATASOURCEINFO entspricht auf die Eigenschaften der Anbieter und der Datenquelle. Das DBPROPSET_DBINIT entspricht den Eigenschaften, die bei der Initialisierung verwendet. Der OLE DB-Anbietervorlagen behandeln diese Sätze mit der PROPERTY_SET-Makros. Die Makros erstellen Sie einen Block, der ein Array von Eigenschaften enthält. Jedes Mal, wenn der Client Ruft die `IDBProperties` -Schnittstelle, den Anbieter verwendet die eigenschaftenzuordnung.

Sie müssen nicht jede Eigenschaft in der Spezifikation zu implementieren. Sie müssen jedoch die erforderlichen Eigenschaften unterstützt. finden Sie unter der Spezifikation der Übereinstimmung mit Standards Level 0 Weitere Informationen. Wenn Sie keine Eigenschaft unterstützen möchten, können Sie es aus der Zuordnung entfernen. Wenn Sie eine Eigenschaft unterstützen möchten, fügen sie in der Zuordnung mit einem PROPERTY_INFO_ENTRY-Makro hinzu. Das Makro entspricht der `UPROPINFO` Struktur wie im folgenden Code gezeigt:

```cpp
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

Jedes Element in der Struktur stellt Informationen zur Behandlung der Eigenschaft dar. Er enthält eine `DBPROPID` um zu bestimmen, die GUID und ID für die Eigenschaft. Sie enthält auch Einträge, um zu bestimmen, den Typ und Wert der Eigenschaft.

Wenn Sie den Standardwert einer Eigenschaft (Beachten Sie, dass ein Consumer den Wert einer beschreibbaren Eigenschaft zu einem beliebigen Zeitpunkt ändern kann) ändern möchten, können Sie entweder die PROPERTY_INFO_ENTRY_VALUE oder PROPERTY_INFO_ENTRY_EX-Makro. Diese Makros können Sie einen Wert für eine entsprechende Eigenschaft angeben. Das PROPERTY_INFO_ENTRY_VALUE-Makro ist eine Kurznotation, die Ihnen ermöglicht, den Wert zu ändern. Das PROPERTY_INFO_ENTRY_VALUE-Makro ruft das PROPERTY_INFO_ENTRY_EX-Makro. Dieses Makro können Sie zum Hinzufügen oder ändern alle Attribute in der `UPROPINFO` Struktur.

Wenn Sie eine eigene Eigenschaft definieren möchten, können Sie ein Set durch eine Kombination von zusätzlichen BEGIN_PROPSET_MAP/END_PROPSET_MAP hinzufügen. Definieren Sie eine GUID für die Eigenschaft festgelegt, und klicken Sie dann definieren Sie eigene Eigenschaften. Wenn Sie anbieterspezifische Eigenschaften haben, fügen sie in eine neue Eigenschaft festlegen, anstatt eine vorhandene Ressourcengruppe hinzu. Dies vermeidet Probleme in späteren Versionen des OLE DB.

## <a name="user-defined-property-sets"></a>Legt für eine benutzerdefinierte Eigenschaft

Visual C++ unterstützt benutzerdefinierte Eigenschaftensätze. Sie müssen keine überschreiben `GetProperties` oder `GetPropertyInfo`. Stattdessen wird die Vorlagen erkennen einen beliebigen Satz eine benutzerdefinierte Eigenschaft, und fügen ihn in das entsprechende Objekt.

Wenn Sie eine benutzerdefinierte Eigenschaft festgelegt haben, die bei der Initialisierung verfügbar sein muss (d. h., bevor der Consumer ruft `IDBInitialize::Initialize`), können Sie dies angeben, indem Sie das UPROPSET_USERINIT-Flag zusammen mit dem BEGIN_PROPERTY_SET_EX-Makro. In das Datenquellenobjekt, damit dies funktioniert (da es sich um eine OLE DB-Spezifikation erfordert), muss die Eigenschaft festgelegt sein. Zum Beispiel:

```cpp
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)
```

## <a name="see-also"></a>Siehe auch

[Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)<br/>
