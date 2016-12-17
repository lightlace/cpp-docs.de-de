---
title: "Anbieterunterst&#252;tzung f&#252;r Lesezeichen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lesezeichen, OLE DB"
  - "IRowsetLocate-Klasse"
  - "IRowsetLocate-Klasse, Anbieterunterstützung für Lesezeichen"
  - "OLE DB-Anbietervorlagen, Lesezeichen"
  - "OLE DB-Anbieter, Lesezeichenunterstützung"
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Anbieterunterst&#252;tzung f&#252;r Lesezeichen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Durch das Beispiel in diesem Thema wird der `CMyProviderRowset`\-Klasse die `IRowsetLocate`\-Schnittstelle hinzugefügt.  In den meisten Fällen beginnen Sie, indem Sie einem bestehenden COM\-Objekt eine Schnittstelle hinzufügen.  Anschließend können Sie das Objekt testen, indem Sie weitere Aufrufe aus den Consumervorlagen hinzufügen.  In diesem Beispiel werden folgende Vorgänge veranschaulicht:  
  
-   Hinzufügen einer Schnittstelle zu einem Anbieter  
  
-   Dynamisches Festlegen der an den Consumer zurückzugebenden Spalten  
  
-   Hinzufügen der Lesezeichenunterstützung  
  
 Die `IRowsetLocate`\-Schnittstelle erbt von der `IRowset`\-Schnittstelle.  Damit die `IRowsetLocate`\-Schnittstelle hinzugefügt werden kann, muss `CMyProviderRowset` von [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md) erben.  
  
 Das Hinzufügen der `IRowsetLocate`\-Schnittstelle unterscheidet sich geringfügig vom Hinzufügen der meisten anderen Schnittstellen.  Die OLE DB\-Anbietervorlagen verfügen über einen Vorlagenparameter zur Behandlung der abgeleiteten Schnittstelle, um die VTABLEs auszurichten.  Im folgenden Code ist die neue Vererbungsliste dargestellt:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 Der vierte, fünfte und sechste Parameter werden alle hinzugefügt.  In diesem Beispiel werden die Standardwerte für den vierten und fünften Parameter verwendet, für den sechsten Parameter wird jedoch `IRowsetLocateImpl` angegeben.  `IRowsetLocateImpl` ist eine OLE\-DB\-Vorlagenklasse, die zwei Vorlagenparameter benötigt: diese verknüpfen die `IRowsetLocate`\-Schnittstelle mit der `CMyProviderRowset`\-Klasse.  Beim Hinzufügen der meisten Schnittstellen können Sie diesen Schritt überspringen und direkt zum nächsten übergehen,  da lediglich die Schnittstellen `IRowsetLocate` und `IRowsetScroll` auf diese Weise behandelt werden müssen.  
  
 Anschließend muss `CMyProviderRowset` angewiesen werden, `QueryInterface` für die `IRowsetLocate`\-Schnittstelle aufzurufen.  Fügen Sie der Zuordnung die Zeile `COM_INTERFACE_ENTRY(IRowsetLocate)` hinzu.  Die Schnittstellenzuordnung für `CMyProviderRowset` sollte wie im folgenden Code aussehen:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Darüber hinaus muss die Zuordnung mit der `CRowsetImpl`\-Klasse verknüpft werden.  Fügen Sie das `-Makro ein, um die CRowsetImpl`\-Zuordnung zu verknüpfen.  Erstellen Sie auch eine Typdefinition mit dem Namen `RowsetBaseClass`, die die Vererbungsinformationen enthält.  Diese Typdefinition ist willkürlich zusammengestellt und kann ignoriert werden.  
  
 Zuletzt muss der **IColumnsInfo::GetColumnsInfo**\-Aufruf verarbeitet werden.  Normalerweise würden Sie zu diesem Zweck die `PROVIDER_COLUMN_ENTRY`\-Makros verwenden.  Beachten Sie jedoch den Fall, dass ein Consumer möglicherweise Lesezeichen verwenden möchte.  Sie müssen dann in der Lage sein, die vom Anbieter zurückgegebenen Spalten abhängig davon zu ändern, ob der Consumer ein Lesezeichen anfordert.  
  
 Um den **IColumnsInfo::GetColumnsInfo**\-Aufruf zu verarbeiten, löschen Sie die **PROVIDER\_COLUMN**\-Zuordnung in der `CTextData`\-Klasse.  Durch das **PROVIDER\_COLUMN\_MAP**\-Makro wird die `GetColumnInfo`\-Funktion definiert.  Sie müssen eine eigene `GetColumnInfo`\-Funktion definieren.  Die Funktionsdeklaration sollte folgendermaßen lauten:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 Implementieren Sie anschließend wie folgt die `GetColumnInfo`\-Funktion in der Datei MyProviderRS.cpp:  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
template <class TInterface>  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   CComQIPtr<TInterface> spProps = pPropsUnk;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spProps)  
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   // Check the property flag for bookmarks, if it is set, set the   
// zero ordinal entry in the column map with the bookmark   
// information.  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,   
                     sizeof(DWORD), DBTYPE_BYTES,  
            0, 0, GUID_NULL, CAgentMan, dwBookmark,         
                        DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
  
   }  
  
   // Next set the other columns up.  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,   
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)  
   ulCols++;  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,  
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
     ULONG* pcCols)  
{  
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),  
        pcCols);  
}  
  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)  
{  
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);  
}  
```  
  
 Zunächst wird durch `GetColumnInfo` überprüft, ob eine Eigenschaft mit dem Namen **DBPROP\_IRowsetLocate** festgelegt wurde.  OLE DB bietet Eigenschaften für alle optionalen Schnittstellen außerhalb des Rowsetobjekts.  Wenn der Consumer eine dieser optionalen Schnittstellen verwenden möchte, setzt er eine Eigenschaft auf **true**.  Daraufhin kann der Anbieter diese Eigenschaft überprüfen und spezielle Aktionen ausführen, die zu ihrer Behandlung erforderlich sind.  
  
 In der Implementierung rufen Sie diese Eigenschaft ab, indem Sie den Zeiger auf das Befehlsobjekt verwenden.  Der `pThis`\-Zeiger stellt die Rowset\- oder Befehlsklasse dar.  Da hier Vorlagen verwendet werden, muss dieser als `void`\-Zeiger übergeben werden, da der Code andernfalls nicht kompiliert wird.  
  
 Legen Sie ein statisches Array zur Aufnahme der Spalteninformationen fest.  Falls die Lesezeichenspalte nicht vom Consumer benötigt wird, bleibt ein Eintrag im Array unbenutzt.  Sie können dieses Array dynamisch reservieren, müssten jedoch sicherstellen, dass es ordnungsgemäß zerstört wird.  In diesem Beispiel werden die Makros **ADD\_COLUMN\_ENTRY** und **ADD\_COLUMN\_ENTRY\_EX** definiert und ausgeführt, um die Informationen in das Array einzufügen.  Sie können die Makros, wie im folgenden Code dargestellt, in die Datei **MyProviderRS.H** einfügen:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 Um den Code im Consumer zu testen, müssen Sie einige Änderungen am `OnRun`\-Handler vornehmen.  Die erste Änderung an der Funktion besteht darin, dass Sie Code hinzufügen, durch den dem Eigenschaftenset eine Eigenschaft hinzugefügt wird.  Durch den Code wird die **DBPROP\_IRowsetLocate**\-Eigenschaft auf **true** gesetzt, wodurch der Anbieter darüber informiert wird, dass die Lesezeichenspalte verwendet werden soll.  Der `OnRun`\-Handlercode sollte wie folgt aussehen:  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
          NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   propset.AddProperty(DBPROP_IRowsetLocate, true);  
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),   
          &propset) != S_OK)  
      return;  
  
   CBookmark<4> tempBookmark;  
   ULONG ulCount=0;  
   while (table.MoveNext() == S_OK)  
   {  
  
      DBCOMPARE compare;  
      if (ulCount == 2)  
         tempBookmark = table.bookmark;  
      HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,  
                 &compare);  
      if (FAILED(hr))  
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);  
      else  
         _ASSERTE(compare == DBCOMPARE_EQ);  
  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
      ulCount++;  
   }  
  
   table.MoveToBookmark(tempBookmark);  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Die `while`\-Schleife enthält Code zum Aufrufen der `Compare`\-Methode in der `IRowsetLocate`\-Schnittstelle.  Der vorhandene Code sollte immer akzeptiert werden, da exakt dieselben Lesezeichen verglichen werden.  Außerdem sollte ein Lesezeichen in einer temporären Variablen gespeichert werden, sodass Sie sie nach Beendigung der `while`\-Schleife verwenden können, um die `MoveToBookmark`\-Funktion in den Consumervorlagen aufzurufen.  Die `MoveToBookmark`\-Funktion ruft die `GetRowsAt`\-Methode in `IRowsetLocate` auf.  
  
 Zusätzlich muss der Benutzerdatensatz im Consumer aktualisiert werden.  Fügen Sie der Klasse und **COLUMN\_MAP** einen Eintrag zur Verarbeitung eines Lesezeichens hinzu:  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
class CProvider  
{  
// Attributes  
public:  
   CBookmark<4>    bookmark;  // Add this line  
   char   szCommand[16];  
   char   szText[256];  
  
   // Binding Maps  
BEGIN_ACCESSOR_MAP(CProvider, 1)  
   BEGIN_ACCESSOR(0, true)   // auto accessor  
      BOOKMARK_ENTRY(bookmark)  // Add this line  
      COLUMN_ENTRY(1, szField1)  
      COLUMN_ENTRY(2, szField2)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 Wenn der Code aktualisiert wurde, sollte es möglich sein, den Anbieter mit der `IRowsetLocate`\-Schnittstelle zu erstellen und auszuführen.  
  
## Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)