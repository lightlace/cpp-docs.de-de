---
title: CDataPathProperty Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2559b4917f16bb8ddc49b73ace8bda6e1a9bafc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367307"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty-Klasse
Implementiert eine OLE-Steuerelementeigenschaft, die asynchron geladen werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Erstellt ein `CDataPathProperty`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|Ruft die asynchrone zugeordneten OLE-Steuerelements die `CDataPathProperty` Objekt.|  
|[CDataPathProperty::GetPath](#getpath)|Ruft den Pfadnamen der Eigenschaft ab.|  
|[CDataPathProperty::Open](#open)|Initialisiert das Laden der asynchronen Eigenschaft für das zugeordnete Steuerelement von ActiveX-(OLE).|  
|[CDataPathProperty::ResetData](#resetdata)|Aufrufe `CAsyncMonikerFile::OnDataAvailable` den Container zu benachrichtigen, dass die Eigenschaften des Steuerelements geändert haben.|  
|[CDataPathProperty::SetControl](#setcontrol)|Legt das asynchrone (OLE)-ActiveX-Steuerelement der Eigenschaft zugeordnet.|  
|[CDataPathProperty::SetPath](#setpath)|Legt den Pfadnamen der Eigenschaft fest.|  
  
## <a name="remarks"></a>Hinweise  
 Asynchrone Eigenschaften werden nach der synchronen Initiierung geladen.  
  
 Die Klasse `CDataPathProperty` stammt aus **CAysncMonikerFile**. Um asynchrone Eigenschaften in die OLE-Steuerelemente implementieren, leiten Sie eine Klasse von `CDataPathProperty`, und überschreiben [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Weitere Informationen zum Verwenden von asynchronen Monikern und ActiveX-Steuerelemente im Internet-Anwendungen finden Sie unter den folgenden Artikeln:  
  
- [Internetgrundlagen: ActiveX-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internetgrundlagen: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="cdatapathproperty"></a>  CDataPathProperty::CDataPathProperty  
 Erstellt ein `CDataPathProperty`-Objekt.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf das OLE-Control-Objekt zugeordnet sein `CDataPathProperty` Objekt.  
  
 `lpszPath`  
 Der Pfad absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die eigentliche absolute Position der Eigenschaft verweist. `CDataPathProperty` URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei, voranstellen `file://` auf den Pfad.  
  
### <a name="remarks"></a>Hinweise  
 Die `COleControl` Objekt verweist `pControl` dient der **öffnen** und abgeleitete Klassen abgerufen. Wenn `pControl` ist **NULL**, das Steuerelement mit verwendet **öffnen** sollte festgelegt werden, mit `SetControl`. Wenn `lpszPath` ist **NULL**, können Sie den Pfad durch übergeben **öffnen** oder legen Sie sie mit `SetPath`.  
  
##  <a name="getcontrol"></a>  CDataPathProperty::GetControl  
 Rufen Sie diese Memberfunktion zum Abrufen der `COleControl` zugeordnete Objekt der `CDataPathProperty` Objekt.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Zeiger auf die OLE-Steuerelements zugeordnet der `CDataPathProperty` Objekt. **NULL** , wenn kein Steuerelement zugeordnet wird.  
  
##  <a name="getpath"></a>  CDataPathProperty::GetPath  
 Rufen Sie diese Memberfunktion zum Abrufen des Pfads festgelegt, wenn die `CDataPathProperty` Objekt erstellt wurde, oder im angegebenen **öffnen**, oder in einem vorherigen Aufruf angegebenen die `SetPath` Memberfunktion.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Pfadnamen für die Eigenschaft selbst zurück. Kann leer sein, wenn kein Pfad angegeben wurde.  
  
##  <a name="open"></a>  CDataPathProperty::Open  
 Rufen Sie diese Memberfunktion zum Laden der asynchronen Eigenschaft für das zugeordnete Steuerelement zu initiieren.  
  
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
 Ein Zeiger auf eine Datei-Ausnahme. Im Falle eines Fehlers wird auf die Ursache festgelegt werden.  
  
 `lpszPath`  
 Der Pfad absolut oder relativ sein kann, verwendet, um eine asynchrone Moniker zu erstellen, die die eigentliche absolute Position der Eigenschaft verweist. `CDataPathProperty` URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei, voranstellen `file://` auf den Pfad.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion versucht, erhalten die `IBindHost` Schnittstelle aus dem Steuerelement.  
  
 Vor dem Aufruf **öffnen** ohne Pfad muss der Wert für den Pfad für die Eigenschaft festgelegt werden. Dies ist möglich, wenn das Objekt konstruierten, oder durch Aufrufen der `SetPath` Memberfunktion.  
  
 Vor dem Aufruf **öffnen** ohne ein Steuerelement kann ein ActiveX-Steuerelement (früher OLE-Steuerelements) kann das Objekt zugeordnet werden. Dies ist möglich, wenn das Objekt konstruierten, oder durch den Aufruf ist `SetControl`.  
  
 Alle Überladungen der [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) stehen auch über `CDataPathProperty`.  
  
##  <a name="resetdata"></a>  CDataPathProperty::ResetData  
 Mit dieser Funktion wird zum Abrufen `CAsyncMonikerFile::OnDataAvailable` auf dem Container zu benachrichtigen, dass die Eigenschaften des Steuerelements geändert haben, und alle Informationen, die asynchron geladen nicht mehr nützlich ist.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Hinweise  
 Öffnende sollte neu gestartet werden. Abgeleitete Klassen können diese Funktion für unterschiedliche Standardwerte überschreiben.  
  
##  <a name="setcontrol"></a>  CDataPathProperty::SetControl  
 Rufen Sie diese Memberfunktion zum Zuordnen eines asynchronen OLE-Steuerelements mit der `CDataPathProperty` Objekt.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Parameter  
 `pControl`  
 Ein Zeiger auf den asynchronen OLE-Steuerelements mit der Eigenschaft zugeordnet werden soll.  
  
##  <a name="setpath"></a>  CDataPathProperty::SetPath  
 Rufen Sie diese Memberfunktion um den Pfadnamen der Eigenschaft festzulegen.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPath`  
 Ein Pfad, die absolut oder relativ ist, für die Eigenschaft, die asynchron geladen werden. `CDataPathProperty` URLs, keine Dateinamen verwendet. Wenn Sie möchten eine `CDataPathProperty` -Objekt für eine Datei, voranstellen `file://` auf den Pfad.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel-Bild](../../visual-cpp-samples.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile-Klasse](../../mfc/reference/casyncmonikerfile-class.md)
