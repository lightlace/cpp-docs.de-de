---
title: CDBVariant-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs: C++
helpviewer_keywords:
- CDBVariant [MFC], CDBVariant
- CDBVariant [MFC], Clear
- CDBVariant [MFC], m_dwType
- CDBVariant [MFC], m_boolVal
- CDBVariant [MFC], m_chVal
- CDBVariant [MFC], m_dblVal
- CDBVariant [MFC], m_fltVal
- CDBVariant [MFC], m_iVal
- CDBVariant [MFC], m_lVal
- CDBVariant [MFC], m_pbinary
- CDBVariant [MFC], m_pdate
- CDBVariant [MFC], m_pstring
- CDBVariant [MFC], m_pstringA
- CDBVariant [MFC], m_pstringW
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 71b19df1d89d07b578156e46a2915bdcd5c70004
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdbvariant-class"></a>CDBVariant-Klasse
Stellt einen varianten Datentyp für die MFC-ODBC-Klassen dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|Erstellt ein `CDBVariant`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|Löscht die `CDBVariant` Objekt.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|Enthält den Datentyp des aktuell gespeicherten Werts an. Geben Sie `DWORD` ein.|  
  
### <a name="public-union-members"></a>Öffentliche Union-Member  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|Enthält einen Wert vom Typ **BOOL**.|  
|[CDBVariant::m_chVal](#m_chval)|Enthält einen Wert vom Typ `unsigned char`.|  
|[CDBVariant::m_dblVal](#m_dblval)|Enthält einen Wert vom Typ **doppelte**.|  
|[CDBVariant::m_fltVal](#m_fltval)|Enthält einen Wert vom Typ **"float"**.|  
|[CDBVariant::m_iVal](#m_ival)|Enthält einen Wert vom Typ **kurze**.|  
|[CDBVariant::m_lVal](#m_lval)|Enthält einen Wert vom Typ **lang**.|  
|[CDBVariant::m_pbinary](#m_pbinary)|Enthält einen Zeiger auf ein Objekt vom Typ `CLongBinary`.|  
|[CDBVariant::m_pdate](#m_pdate)|Enthält einen Zeiger auf ein Objekt des Typs **TIMESTAMP_STRUCT**.|  
|[CDBVariant::m_pstring](#m_pstring)|Enthält einen Zeiger auf ein Objekt vom Typ `CString`.|  
|[CDBVariant::m_pstringA](#m_pstringa)|Speichert einen Zeiger auf ein ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.|  
|[CDBVariant::m_pstringW](#m_pstringw)|Speichert einen Zeiger auf eine Vielzahl [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CDBVariant`eine Basisklasse verfügt nicht über.  
  
 `CDBVariant`ähnelt dem [COleVariant](../../mfc/reference/colevariant-class.md)jedoch `CDBVariant` verwendet keinen OLE. `CDBVariant`können Sie einen Wert zu speichern, ohne befürchten Datentyp des Werts. `CDBVariant`verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.  
  
 Klasse [CRecordset](../../mfc/reference/crecordset-class.md) nutzt `CDBVariant` Objekte in drei Memberfunktionen: `GetFieldValue`, `GetBookmark`, und `SetBookmark`. Beispielsweise `GetFieldValue` ermöglicht Ihnen, Daten in einer Spalte dynamisch abzurufen. Da der Datentyp der Spalte nicht zur Laufzeit möglicherweise feststeht `GetFieldValue` verwendet eine `CDBVariant` Objekt zum Speichern von Daten in der Spalte.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CDBVariant`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="cdbvariant"></a>CDBVariant::CDBVariant  
 Erstellt ein NULL-Wert `CDBVariant` Objekt.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>Hinweise  
 Legt die [M_dwType](#m_dwtype) Datenmember **DBVT_NULL**.  
  
##  <a name="clear"></a>CDBVariant::Clear  
 Rufen Sie diese Memberfunktion zum Deaktivieren der `CDBVariant` Objekt.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Wert der [M_dwType](#m_dwtype) -Datenmember ist **DBVT_DATE**, **DBVT_STRING**, oder **DBVT_BINARY**, **deaktivieren**gibt den Arbeitsspeicher frei der union Zeiger-Element zugeordnet sind. **Clear** legt `m_dwType` auf **DBVT_NULL**.  
  
 Die `CDBVariant` Destruktoraufrufe **löschen**.  
  
##  <a name="m_boolval"></a>CDBVariant::m_boolVal  
 Speichert einen Wert vom Typ **BOOL**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_boolVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_boolVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_BOOL**, klicken Sie dann **M_boolVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_boolVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_chval"></a>CDBVariant::m_chVal  
 Speichert einen Wert vom Typ `unsigned char`.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_chVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_chVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_UCHAR**, klicken Sie dann **M_chVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_chVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_dblval"></a>CDBVariant::m_dblVal  
 Speichert einen Wert vom Typ **doppelte**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_dblVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_dblVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_DOUBLE**, klicken Sie dann **M_dblVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_dblVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_dwtype"></a>CDBVariant::m_dwType  
 Dieses Datenelement enthält den Datentyp für den Wert an, die derzeit in gespeichert ist die `CDBVariant` die union-Datenmember des Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Zugriff auf diese Union, überprüfen Sie den Wert der `m_dwType` um zu bestimmen, welche union-Datenmember auf. Die folgende Tabelle enthält die möglichen Werte für `m_dwType` und die entsprechenden union-Datenmember.  
  
|m_dwType|Union-Datenmember|  
|---------------|-----------------------|  
|**DBVT_NULL**|Keine union-Member ist gültig für den Zugriff.|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>CDBVariant::m_fltVal  
 Speichert einen Wert vom Typ **"float"**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_fltVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_fltVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_SINGLE**, klicken Sie dann **M_fltVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_fltVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_ival"></a>CDBVariant::m_iVal  
 Speichert einen Wert vom Typ **kurze**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_iVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_iVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_SHORT**, klicken Sie dann **M_iVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_iVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_lval"></a>CDBVariant::m_lVal  
 Speichert einen Wert vom Typ **lang**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_lVal** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_lVal**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_LONG**, klicken Sie dann **M_lVal** einen gültigen Wert enthält; andernfalls, den Zugriff auf **M_lVal** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_pbinary"></a>CDBVariant::m_pbinary  
 Speichert einen Zeiger auf ein Objekt des Typs [CLongBinary](../../mfc/reference/clongbinary-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Die **M_pbinary** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_pbinary**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_BINARY**, klicken Sie dann **M_pbinary** enthält einen gültigen Zeiger; andernfalls, den Zugriff auf **M_pbinary** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_pdate"></a>CDBVariant::m_pdate  
 Speichert einen Zeiger auf ein Objekt des Typs **TIMESTAMP_STRUCT**.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_pdate** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_pdate**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_DATE**, klicken Sie dann **M_pdate** enthält einen gültigen Zeiger; andernfalls, den Zugriff auf **M_pdate** wird zu unzuverlässige Ergebnissen führen.  
  
 Weitere Informationen zu den **TIMESTAMP_STRUCT** -Datentyp, finden Sie im Thema [C-Datentypen](https://msdn.microsoft.com/library/ms714556.aspx) in Anhang D der *ODBC Programmer's Reference* im Windows SDK.  
  
##  <a name="m_pstring"></a>CDBVariant::m_pstring  
 Speichert einen Zeiger auf ein Objekt des Typs [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Die **M_pstring** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_pstring**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_STRING**, klicken Sie dann **M_pstring** enthält einen gültigen Zeiger; andernfalls, den Zugriff auf **M_pstring** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_pstringa"></a>CDBVariant::m_pstringA  
 Speichert einen Zeiger auf ein ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_pstringA** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_pstringA**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_ASTRING**, klicken Sie dann **M_pstringA** enthält einen gültigen Zeiger; andernfalls, den Zugriff auf **M_pstringA** wird zu unzuverlässige Ergebnissen führen.  
  
##  <a name="m_pstringw"></a>CDBVariant::m_pstringW  
 Speichert einen Zeiger auf eine Vielzahl [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die **M_pstringW** -Datenmember auf eine Union gehört. Vor dem Zugriff auf **M_pstringW**, überprüfen Sie zunächst den Wert der [CDBVariant::m_dwType](#m_dwtype). Wenn `m_dwType` festgelegt ist, um **DBVT_WSTRING**, klicken Sie dann **M_pstringW** enthält einen gültigen Zeiger; andernfalls, den Zugriff auf **M_pstringW** wird zu unzuverlässige Ergebnissen führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)
