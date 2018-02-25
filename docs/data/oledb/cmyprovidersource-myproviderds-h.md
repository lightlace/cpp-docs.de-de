---
title: CMyProviderSource (MyProviderDS.H) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- myproviderds.h
- cmyprovidersource
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderSource class in MyProviderDS.H
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0bdb766abd034868fe12fc0913fbdd99287b9e4f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cmyprovidersource-myproviderdsh"></a>CMyProviderSource (MyProviderDS.H)
Die-Anbieterklassen verwenden mehrfache Vererbung. Der folgende Code zeigt die Vererbungskette für das Datenquellenobjekt:  
  
```cpp
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
  
 Leiten Sie die COM-Komponenten von `CComObjectRootEx` und `CComCoClass`. `CComObjectRootEx` Stellt die Implementierung für die **IUnknown** Schnittstelle. Es kann Threadingmodell behandeln. `CComCoClass` behandelt alle Fehler Unterstützung erforderlich sind. Wenn Sie ausführlichere Fehlerinformationen an den Client senden möchten, können Sie einige der Fehler-APIs in `CComCoClass`.  
  
 Das Datenquellenobjekt erbt auch von mehreren "Impl"-Klassen. Jede Klasse stellt die Implementierung für eine Schnittstelle bereit. Das Datenquellenobjekt implementiert die `IPersist`, `IDBProperties`, **IDBInitialize**, und **IDBCreateSession** Schnittstellen. Jede Schnittstelle vom OLE DB-erforderlich werden, um das Datenquellenobjekt zu implementieren. Sie können auswählen, zu unterstützen, oder erben oder erben nicht von einer dieser Klassen "Impl" bestimmte Funktionen nicht unterstützt. Wenn Sie unterstützen möchten die **IDBDataSourceAdmin** Schnittstelle erben von der **IDBDataSourceAdminImpl** Klasse, um die erforderliche Funktionalität zu erhalten.  
  
## <a name="com-map"></a>COM-Zuordnung  
 Wenn der Client ruft `QueryInterface` für eine Schnittstelle für die Datenquelle, durchläuft es die folgenden COM-Zuordnung:  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 Die COM_INTERFACE_ENTRY-Makros sind von ATL und weisen die Implementierung von `QueryInterface` in `CComObjectRootEx` die entsprechenden Schnittstellen zurückgegeben.  
  
## <a name="property-map"></a>Eigenschaftenzuordnung  
 Die eigenschaftenzuordnung gibt die Eigenschaften, die vom Anbieter festgelegt:  
  
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
  
 Eigenschaften in der OLE DB gruppiert sind. Das Datenquellenobjekt verfügt über zwei Gruppen von Eigenschaften: einen für die **DBPROPSET_DATASOURCEINFO** festlegen und eine für die **DBPROPSET_DBINIT** festgelegt. Die **DBPROPSET_DATASOURCEINFO** auf die Eigenschaften des Anbieters und seiner Datenquelle entspricht. Die **DBPROPSET_DBINIT** entspricht den Eigenschaften, die bei der Initialisierung verwendet. Der OLE DB-Anbietervorlagen behandeln diese Sätze mit der PROPERTY_SET-Makros. Die Makros erstellen Sie einen Block, der ein Array von Eigenschaften enthält. Wenn der Client Ruft die `IDBProperties` -Schnittstelle, den Anbieter verwendet die eigenschaftenzuordnung.  
  
 Sie müssen nicht jede Eigenschaft in der Spezifikation zu implementieren. Allerdings müssen Sie die erforderlichen Eigenschaften unterstützt; finden Sie in der Spezifikation der Ebene 0-Konformität für Weitere Informationen. Wenn Sie nicht, um eine Eigenschaft zu unterstützen möchten, können Sie es aus der Zuordnung entfernen. Wenn Sie eine Eigenschaft unterstützen möchten, fügen Sie ihn in die Zuordnung, mit einem PROPERTY_INFO_ENTRY-Makro. Das Makro entspricht der **UPROPINFO** Struktur wie im folgenden Code gezeigt:  
  
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
  
 Jedes Element in der Struktur stellt Informationen zur Behandlung der Eigenschaft dar. Er enthält eine **DBPROPID** den GUID und die ID für die Eigenschaft zu bestimmen. Es enthält auch Einträge, um den Typ und Wert der Eigenschaft zu bestimmen.  
  
 Wenn Sie den Standardwert einer Eigenschaft (Beachten Sie, dass ein Consumer den Wert einer beschreibbaren Eigenschaft jederzeit ändern kann) ändern möchten, können Sie entweder die PROPERTY_INFO_ENTRY_VALUE oder PROPERTY_INFO_ENTRY_EX-Makro verwenden. Diese Makros können Sie einen Wert für eine entsprechende Eigenschaft angeben. PROPERTY_INFO_ENTRY_VALUE-Makro ist eine Kurzschreibweise, die Ihnen ermöglicht, den Wert zu ändern. PROPERTY_INFO_ENTRY_VALUE-Makro ruft PROPERTY_INFO_ENTRY_EX-Makro. Dieses Makro können Sie zum Hinzufügen oder ändern alle Attribute in der **UPROPINFO** Struktur.  
  
 Wenn Sie eine eigene Eigenschaft definieren möchten, können Sie ein Set durch eine zusätzliche BEGIN_PROPSET_MAP/END_PROPSET_MAP-Kombination hinzufügen. Definieren eine GUID für die Eigenschaft festgelegt, und definieren Sie eine eigene Eigenschaften werden müssen. Wenn Sie die anbieterspezifischen Eigenschaften haben, fügen Sie eine neue Eigenschaft anstatt eine vorhandene festgelegt. Dadurch wird vermieden, in höheren Versionen des OLE DB-Probleme.  
  
## <a name="user-defined-property-sets"></a>Legt eine benutzerdefinierte Eigenschaft  
 Visual C++ unterstützt benutzerdefinierte Eigenschaftensätze. Sie müssen nicht außer Kraft setzen **GetProperties** oder `GetPropertyInfo`. Stattdessen die Vorlagen alle benutzerdefinierten Eigenschaftensatz erkennen und fügen ihn in das entsprechende Objekt.  
  
 Haben eine Reihe eine benutzerdefinierte Eigenschaft, die bei der Initialisierung des verfügbar sein muss (d. h., bevor der Consumer ruft **IDBInitialize:: Initialize**), können Sie dies angeben, mit der **UPROPSET_USERINIT** Flag in Verbindung mit dem BEGIN_PROPERTY_SET_EX-Makro. Der festgelegte Eigenschaft muss in das Datenquellenobjekt dafür festlegen (wie die OLE DB-Spezifikation erfordert). Zum Beispiel:  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Vom Anbieter-Assistenten generierte Dateien](../../data/oledb/provider-wizard-generated-files.md)