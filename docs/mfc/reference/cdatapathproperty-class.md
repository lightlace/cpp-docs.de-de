---
title: CDataPathProperty-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- CDataPathProperty class
- asynchronous controls [C++]
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d767cf950d8b86959aadc2fd4d77401134a6dc75
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdatapathproperty-class"></a>CDataPathProperty-Klasse
Implementiert eine OLE-Steuerelementeigenschaft, die asynchron geladen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Erstellt ein `CDataPathProperty`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|Ruft das asynchrone zugeordnete OLE-Steuerelement die `CDataPathProperty` Objekt.|  
|[CDataPathProperty::GetPath](#getpath)|Ruft den Pfadnamen der Eigenschaft ab.|  
|[CDataPathProperty::Open](#open)|Initialisiert das Laden der asynchronen-Eigenschaft für das zugeordnete (OLE)-ActiveX-Steuerelement.|  
|[CDataPathProperty::ResetData](#resetdata)|Aufrufe `CAsyncMonikerFile::OnDataAvailable` Benachrichtigung des Containers, die Eigenschaften des Steuerelements geändert wurden.|  
|[CDataPathProperty::SetControl](#setcontrol)|Legt das asynchrone ActiveX (OLE)-Steuerelement, das der Eigenschaft zugeordnet.|  
|[CDataPathProperty::SetPath](#setpath)|Legt den Pfadnamen der Eigenschaft fest.|  
  
## <a name="remarks"></a>Hinweise  
 Asynchrone Eigenschaften werden nach der synchronen Initiierung geladen.  
  
 Die Klasse `CDataPathProperty` stammt von **CAysncMonikerFile**. Um asynchrone Eigenschaften in die OLE-Steuerelemente zu implementieren, leiten Sie eine Klasse von `CDataPathProperty`, und überschreiben Sie [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Weitere Informationen zur Verwendung von asynchronen Monikern und ActiveX-Steuerelemente im Internet Applications finden Sie unter den folgenden Artikeln:  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty  
 Erstellt ein `CDataPathProperty`-Objekt.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf das OLE-Control-Objekt zugeordnet sein `CDataPathProperty` Objekt.  
  
 `lpszPath`  
 Der Pfad, der absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die tatsächliche absolute Position der Eigenschaft verweist. `CDataPathProperty`URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei und voranstellen `file://` auf den Pfad.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleControl` Objekt verweist `pControl` werden **öffnen** und von abgeleiteten Klassen abgerufen. Wenn `pControl` ist **NULL**, das Steuerelement mit **öffnen** sollte festgelegt werden, mit `SetControl`. Wenn `lpszPath` ist **NULL**, können Sie den Pfad durch übergeben **öffnen** oder legen Sie sie mit `SetPath`.  
  
##  <a name="getcontrol"></a>CDataPathProperty::GetControl  
 Rufen Sie diese Memberfunktion zum Abrufen der `COleControl` zugeordnete Objekt der `CDataPathProperty` Objekt.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Zeiger auf das OLE-Steuerelement zugeordnete der `CDataPathProperty` Objekt. **NULL** , wenn kein Steuerelement zugeordnet wird.  
  
##  <a name="getpath"></a>CDataPathProperty::GetPath  
 Rufen Sie diese Memberfunktion zum Abrufen des Pfads festgelegt, wenn die `CDataPathProperty` Objekt erstellt wurde, oder im angegebenen **öffnen**, oder in einem vorherigen Aufruf angegebenen der `SetPath` Member-Funktion.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Pfadnamen für die Eigenschaft selbst zurück. Kann leer sein, wenn kein Pfad angegeben wurde.  
  
##  <a name="open"></a>CDataPathProperty::Open  
 Rufen Sie diese Memberfunktion zum Laden der asynchronen-Eigenschaft für das zugeordnete Steuerelement zu initiieren.  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf das OLE-Control-Objekt zugeordnet sein `CDataPathProperty` Objekt.  
  
 `pError`  
 Ein Zeiger auf eine Datei ausgelöst. Im Falle eines Fehlers werden auf die Ursache festgelegt.  
  
 `lpszPath`  
 Der Pfad, der absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die tatsächliche absolute Position der Eigenschaft verweist. `CDataPathProperty`URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei und voranstellen `file://` auf den Pfad.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion versucht, erhalten die `IBindHost` Schnittstelle aus dem Steuerelement.  
  
 Vor dem Aufruf von **öffnen** ohne Pfad, muss der Wert für die Eigenschaft Pfad festgelegt werden. Dies ist möglich, wenn das Objekt erstellten, oder durch Aufrufen der `SetPath` Member-Funktion.  
  
 Vor dem Aufruf von **öffnen** ohne ein Steuerelement kann ein ActiveX-Steuerelement (früher als OLE-Steuerelement bezeichnet) für das Objekt sein. Dies ist möglich, wenn das Objekt erstellten, oder durch Aufrufen von `SetControl`.  
  
 Alle Überladungen der [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) können auch von `CDataPathProperty`.  
  
##  <a name="resetdata"></a>CDataPathProperty::ResetData  
 Rufen Sie diese Funktion zum Abrufen des `CAsyncMonikerFile::OnDataAvailable` auf dem Container zu benachrichtigen, dass die Steuerelementeigenschaften geändert haben, und alle Informationen, die asynchron geladen nicht mehr nützlich ist.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Hinweise  
 Öffnen sollte neu gestartet werden. Abgeleitete Klassen können diese Funktion für unterschiedliche Standardwerte überschreiben.  
  
##  <a name="setcontrol"></a>CDataPathProperty::SetControl  
 Rufen Sie diese Memberfunktion zum Zuordnen eines asynchronen OLE-Steuerelements mit der `CDataPathProperty` Objekt.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf die asynchrone OLE-Steuerelement die Eigenschaft zugeordnet werden soll.  
  
##  <a name="setpath"></a>CDataPathProperty::SetPath  
 Rufen Sie diese Memberfunktion um den Pfadnamen der Eigenschaft festzulegen.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPath`  
 Ein Pfad, der absolute oder relative, auf die Eigenschaft, die asynchron geladen werden kann. `CDataPathProperty`URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei und voranstellen `file://` auf den Pfad.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Bild](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)

