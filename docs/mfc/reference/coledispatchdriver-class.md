---
title: COleDispatchDriver Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchDriver
- AFXDISP/COleDispatchDriver
- AFXDISP/COleDispatchDriver::COleDispatchDriver
- AFXDISP/COleDispatchDriver::AttachDispatch
- AFXDISP/COleDispatchDriver::CreateDispatch
- AFXDISP/COleDispatchDriver::DetachDispatch
- AFXDISP/COleDispatchDriver::GetProperty
- AFXDISP/COleDispatchDriver::InvokeHelper
- AFXDISP/COleDispatchDriver::ReleaseDispatch
- AFXDISP/COleDispatchDriver::SetProperty
- AFXDISP/COleDispatchDriver::m_bAutoRelease
- AFXDISP/COleDispatchDriver::m_lpDispatch
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchDriver [MFC], COleDispatchDriver
- COleDispatchDriver [MFC], AttachDispatch
- COleDispatchDriver [MFC], CreateDispatch
- COleDispatchDriver [MFC], DetachDispatch
- COleDispatchDriver [MFC], GetProperty
- COleDispatchDriver [MFC], InvokeHelper
- COleDispatchDriver [MFC], ReleaseDispatch
- COleDispatchDriver [MFC], SetProperty
- COleDispatchDriver [MFC], m_bAutoRelease
- COleDispatchDriver [MFC], m_lpDispatch
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 059ff922689eaf354d4b4ae9b89fb49ab8c5a885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coledispatchdriver-class"></a>COleDispatchDriver-Klasse
Implementiert die Clientseite der OLE-Automatisierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleDispatchDriver  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](#coledispatchdriver)|Erstellt ein `COleDispatchDriver`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDispatchDriver::AttachDispatch](#attachdispatch)|Fügt eine `IDispatch` Verbindung mit der `COleDispatchDriver` Objekt.|  
|[COleDispatchDriver:: CreateDispatch](#createdispatch)|Erstellt ein `IDispatch` Verbindung und fügt es der `COleDispatchDriver` Objekt.|  
|[COleDispatchDriver::DetachDispatch](#detachdispatch)|Trennt eine `IDispatch` Verbindung, ohne es freizugeben.|  
|[COleDispatchDriver:: GetProperty](#getproperty)|Ruft ein Automatisierungseigenschaft ab.|  
|[COleDispatchDriver:: InvokeHelper](#invokehelper)|Hilfsprogramm für die Automatisierungsmethoden aufrufen.|  
|[COleDispatchDriver::ReleaseDispatch](#releasedispatch)|Versionen eine `IDispatch` Verbindung.|  
|[Schlüsselwörter COleDispatchDriver:: SetProperty](#setproperty)|Legt eine Automatisierungseigenschaft fest.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDispatchDriver::operator =](#operator_eq)|Kopiert den Quellwert in den `COleDispatchDriver` Objekt.|  
|[COleDispatchDriver::operator LPDISPATCH](#operator_lpdispatch)|Greift auf die zugrunde liegende `IDispatch` Zeiger.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDispatchDriver::m_bAutoRelease](#m_bautorelease)|Gibt an, ob die Version der `IDispatch` während `ReleaseDispatch` oder auf die Zerstörung.|  
|[COleDispatchDriver::m_lpDispatch](#m_lpdispatch)|Gibt an, die Zeiger auf die `IDispatch` Schnittstelle angefügte `COleDispatchDriver`.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDispatchDriver`eine Basisklasse verfügt nicht über.  
  
 OLE-Dispatch-Schnittstellen bieten Zugriff auf die Methoden und Eigenschaften des Objekts. Memberfunktionen von `COleDispatchDriver` anfügen, trennen, erstellen und Freigeben eine Dispatch-Verbindung vom Typ `IDispatch`. Andere Memberfunktionen verwenden Argumentlisten variabler Länge zum Aufrufen von vereinfachen **IDispatch:: Invoke**.  
  
 Diese Klasse kann direkt verwendet werden, aber es im Allgemeinen wird nur von Klassen, die vom Assistenten zum Hinzufügen von Klassen erstellt. Wenn Sie die neue C++-Klassen erstellen, durch das Importieren einer Typbibliothek, die neuen Klassen abgeleitet sind `COleDispatchDriver`.  
  
 Weitere Informationen zur Verwendung von `COleDispatchDriver`, finden Sie unter den folgenden Artikeln:  
  
- [Automatisierungsclients](../../mfc/automation-clients.md)  
  
- [Automatisierungsserver](../../mfc/automation-servers.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `COleDispatchDriver`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="attachdispatch"></a>COleDispatchDriver::AttachDispatch  
 Rufen Sie die `AttachDispatch` -Memberfunktion auf, um dem `IDispatch` -Objekt einen `COleDispatchDriver` -Zeiger anzufügen. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
```  
void AttachDispatch(
        LPDISPATCH lpDispatch,  
        BOOL bAutoRelease = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDispatch`  
 Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.  
  
 `bAutoRelease`  
 Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gibt alle `IDispatch` -Zeiger zurück, die dem `COleDispatchDriver` -Objekt bereits angefügt wurden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#3](../../mfc/codesnippet/cpp/coledispatchdriver-class_1.cpp)]  
  
##  <a name="coledispatchdriver"></a>COleDispatchDriver::COleDispatchDriver  
 Erstellt ein `COleDispatchDriver`-Objekt.  
  
```  
COleDispatchDriver();  
COleDispatchDriver(LPDISPATCH lpDispatch, BOOL bAutoRelease = TRUE);  
  COleDispatchDriver(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDispatch`  
 Zeiger auf ein `IDispatch` -OLE-Objekt, der an das `COleDispatchDriver` -Objekt angefügt werden soll.  
  
 `bAutoRelease`  
 Gibt an, ob die Verteilung freigegeben werden soll, wenn dieses Objekt den Gültigkeitsbereich verlässt.  
  
 `dispatchSrc`  
 Ein Verweis auf ein vorhandenes `COleDispatchDriver` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Formular `COleDispatchDriver`( `LPDISPATCH lpDispatch`, **BOOL**`bAutoRelease` = **"true"**) verbindet die [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) Schnittstelle.  
  
 Das Formular `COleDispatchDriver`( **const**`COleDispatchDriver`& `dispatchSrc`) kopiert eine vorhandene `COleDispatchDriver` Objekt, und inkrementiert den Verweiszähler dieser Planergruppe.  
  
 Das Formular `COleDispatchDriver`() erstellt eine `COleDispatchDriver` Objekt aber keine Verbindung her der `IDispatch` Schnittstelle. Vor der Verwendung `COleDispatchDriver`(ohne Argumente), sollten Sie verbinden ein `IDispatch` entweder mit [COleDispatchDriver:: CreateDispatch](#createdispatch) oder [COleDispatchDriver::AttachDispatch](#attachdispatch). Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](#createdispatch).  
  
##  <a name="createdispatch"></a>COleDispatchDriver:: CreateDispatch  
 Erstellt ein [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) -Schnittstellenobjekt und fügt es der `COleDispatchDriver` Objekt.  
  
```  
BOOL CreateDispatch(
        REFCLSID clsid,  
        COleException* pError = NULL);

 
BOOL CreateDispatch(
    LPCTSTR lpszProgID,  
    COleException* pError = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `clsid`  
 Die Klassen-ID, des zu erstellenden `IDispatch` -Verbindungsobjekts.  
  
 `pError`  
 Ein Zeiger auf ein OLE-Ausnahmeobjekt, das den Statuscode aufnimmt, der sich durch die Erstellung ergibt.  
  
 `lpszProgID`  
 Ein Zeiger auf den programmgesteuerten Bezeichner, z. B. „Excel.Document.5“, des Automatisierungsobjekts, für das das Dispatch-Objekt erstellt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg ein Wert ungleich 0 (null), andernfalls 0 (null).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#4](../../mfc/codesnippet/cpp/coledispatchdriver-class_2.cpp)]  
  
##  <a name="detachdispatch"></a>COleDispatchDriver::DetachDispatch  
 Trennt die aktuelle `IDispatch` Verbindung von diesem Objekt.  
  
```  
LPDISPATCH DetachDispatch();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zuvor angefügten OLE `IDispatch` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die `IDispatch` wird nicht freigegeben.  
  
 Weitere Informationen zu den `LPDISPATCH` finden Sie unter [Implementieren der IDispatch-Schnittstelle](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#5](../../mfc/codesnippet/cpp/coledispatchdriver-class_3.cpp)]  
  
##  <a name="getproperty"></a>COleDispatchDriver:: GetProperty  
 Ruft die Objekteigenschaft, die vom angegebenen `dwDispID`.  
  
```  
void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Bezeichnet die Eigenschaft abgerufen werden sollen.  
  
 `vtProp`  
 Gibt die Eigenschaft abgerufen werden sollen. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](#invokehelper).  
  
 `pvProp`  
 Die Adresse der Variablen, die den Wert der Eigenschaft zugewiesen wird. Mit den vom angegebenen Typ übereinstimmen muss `vtProp`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#6](../../mfc/codesnippet/cpp/coledispatchdriver-class_4.cpp)]  
  
##  <a name="invokehelper"></a>COleDispatchDriver:: InvokeHelper  
 Ruft die von `dwDispID`angegebene Objektmethode oder -eigenschaft in dem durch `wFlags`angegebenen Kontext auf.  
  
```  
void AFX_CDECL InvokeHelper(
        DISPID dwDispID,  
        WORD wFlags,  
        VARTYPE vtRet,  
        void* pvRet,  
        const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Bezeichnet die aufzurufende Methode oder Eigenschaft.  
  
 `wFlags`  
 Flags, die den Kontext des Aufrufs von **IDispatch::Invoke**beschreiben. sein. Eine Liste der möglichen Werte finden Sie unter der `wFlags` im Parameters [IDispatch:: Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) im Windows SDK.  
  
 `vtRet`  
 Gibt den Typ des Rückgabewerts an. Mögliche Werte finden Sie im Abschnitt „Hinweise“.  
  
 `pvRet`  
 Die Adresse der Variablen, die den Eigenschaftswert oder Rückgabewert aufnimmt. Sie muss mit dem durch `vtRet`angegebenen Typ übereinstimmen.  
  
 `pbParamInfo`  
 Zeiger auf eine NULL-terminierte Zeichenfolge aus Bytes, die die Typen der Parameter angeben, die auf `pbParamInfo`folgen.  
  
 *...*  
 Variable Parameterliste aus den in `pbParamInfo`angegebenen Typen.  
  
### <a name="remarks"></a>Hinweise  
 Der `pbParamInfo` -Parameter gibt die Typen der an die Methode oder Eigenschaft übergebenen Parameter an. Die variable Argumentliste wird in der Syntaxdeklaration durch **...** dargestellt.  
  
 Die möglichen Werte des `vtRet` -Arguments werden der `VARENUM` -Enumeration entnommen. Folgende Werte sind möglich:  
  
|Symbol|Rückgabetyp|  
|------------|-----------------|  
|`VT_EMPTY`|`void`|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
|`VT_CY`|**CY**|  
|`VT_DATE`|**DATE**|  
|`VT_BSTR`|`BSTR`|  
|**VT_DISPATCH**|`LPDISPATCH`|  
|`VT_ERROR`|`SCODE`|  
|`VT_BOOL`|**BOOL**|  
|**VT_VARIANT**|**VARIANT**|  
|**VT_UNKNOWN**|`LPUNKNOWN`|  
  
 Das `pbParamInfo` -Argument ist eine durch Leerzeichen getrennte Liste aus **VTS_** -Konstanten. Einer oder mehrere dieser Werte, durch Leerzeichen (nicht Kommas) getrennt, gibt bzw. geben die Parameterliste der Funktion an. Mögliche Werte sind aufgeführt, mit der [EVENT_CUSTOM](event-maps.md#event_custom) Makro.  
  
 Diese Funktion konvertiert die Parameter in Werte von **VARIANTARG** und ruft anschließend die Methode [IDispatch::Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx) auf. Bei einem Fehler des Aufrufs von `Invoke` löst diese Funktion eine Ausnahme aus. Wenn die `SCODE` (Statuscode) zurückgegebene **IDispatch:: Invoke** ist `DISP_E_EXCEPTION`, diese Funktion löst einen [COleException](../../mfc/reference/coleexception-class.md) Objekt; andernfalls löst eine [ COleDispatchException](../../mfc/reference/coledispatchexception-class.md).  
  
 Weitere Informationen finden Sie unter [VARIANTARG](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [Implementieren der IDispatch-Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/ms221037\(v=vs.85\).aspx), [IDispatch:: Invoke](http://msdn.microsoft.com/library/windows/desktop/ms221479\(v=vs.85\).aspx), und [Struktur von COM-Fehlercodes](http://msdn.microsoft.com/library/windows/desktop/ms690088) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver:: CreateDispatch](#createdispatch).  
  
##  <a name="m_bautorelease"></a>COleDispatchDriver::m_bAutoRelease  
 Wenn **"true"**, die COM-Objekt zugegriffen [M_lpDispatch](#m_lpdispatch) automatisch freigegeben, wenn [ReleaseDispatch](#releasedispatch) aufgerufen wird oder wenn dies `COleDispatchDriver` Objekt ist zerstört.  
  
```  
BOOL m_bAutoRelease;  
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig `m_bAutoRelease` festgelegt ist, um **"true"** im Konstruktor.  
  
 Weitere Informationen zur Freigabe von COM-Objekten finden Sie unter [Verweiszählung implementieren](http://msdn.microsoft.com/library/windows/desktop/ms693431) und [IUnknown:: Release](http://msdn.microsoft.com/library/windows/desktop/ms682317) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#9](../../mfc/codesnippet/cpp/coledispatchdriver-class_5.cpp)]  
  
##  <a name="m_lpdispatch"></a>COleDispatchDriver::m_lpDispatch  
 Der Zeiger auf die `IDispatch` Schnittstelle angefügte `COleDispatchDriver`.  
  
```  
LPDISPATCH m_lpDispatch;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `m_lpDispatch` -Datenmember ist eine öffentliche Variable des Typs `LPDISPATCH`.  
  
 Weitere Informationen finden Sie unter [IDispatch](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="operator_eq"></a>COleDispatchDriver::operator =  
 Kopiert den Quellwert in den `COleDispatchDriver` Objekt.  
  
```  
const COleDispatchDriver& operator=(const COleDispatchDriver& dispatchSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `dispatchSrc`  
 Ein Zeiger auf ein vorhandenes `COleDispatchDriver` Objekt.  
  
##  <a name="operator_lpdispatch"></a>COleDispatchDriver::operator LPDISPATCH  
 Greift auf die zugrunde liegende `IDispatch` Zeiger, der die `COleDispatchDriver` Objekt.  
  
```  
operator LPDISPATCH();
```   
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#8](../../mfc/codesnippet/cpp/coledispatchdriver-class_6.cpp)]  
  
##  <a name="releasedispatch"></a>COleDispatchDriver::ReleaseDispatch  
 Versionen der `IDispatch` Verbindung. Weitere Informationen finden Sie unter [Implementieren der IDispatch-Schnittstelle](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945)  
  
```  
void ReleaseDispatch();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die automatische Freigabe für diese Verbindung festgelegt wurde, wird diese Funktion ruft **IDispatch::Release** vor dem Freigeben von der Schnittstelle.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [COleDispatchDriver::AttachDispatch](#attachdispatch).  
  
##  <a name="setproperty"></a>Schlüsselwörter COleDispatchDriver:: SetProperty  
 Legt die durch `dwDispID`angegebene OLE-Objekteigenschaft fest.  
  
```  
void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>Parameter  
 `dwDispID`  
 Gibt die festzulegende Eigenschaft an.  
  
 `vtProp`  
 Gibt den Typ der festzulegenden Eigenschaft an. Mögliche Werte finden Sie im Abschnitt "Hinweise" [COleDispatchDriver:: InvokeHelper](#invokehelper).  
  
 *...*  
 Ein einzelner Parameter des durch `vtProp`angegebenen Typs.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#7](../../mfc/codesnippet/cpp/coledispatchdriver-class_7.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)   
 [MFC-Beispiel ACDUAL](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CCmdTarget-Klasse](../../mfc/reference/ccmdtarget-class.md)
