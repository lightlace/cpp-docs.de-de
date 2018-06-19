---
title: CPropExchange Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f234b3f06e22308a31e8e5694648fd5664b448a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377339"
---
# <a name="cpropexchange-class"></a>CPropExchange-Klasse
Unterstützt die Implementierung der Dauerhaftigkeit für die OLE-Steuerelemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Tauscht eine binary large Object (BLOB)-Eigenschaft.|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Tauscht eine Schriftarteigenschaft.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Tauscht eine Eigenschaft zwischen einem Steuerelement und einer Datei an.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Tauscht die Eigenschaften eines beliebigen integrierten Typs.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|Tauscht die Versionsnummer eines OLE-Steuerelements an.|  
|[CPropExchange::GetVersion](#getversion)|Ruft die Versionsnummer eines OLE-Steuerelements ab.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Bestimmt, ob die Eigenschaft Nachrichtenaustausch asynchron ausgeführt werden.|  
|[CPropExchange::IsLoading](#isloading)|Gibt an, ob die Eigenschaften werden in das Steuerelement geladen oder daraus gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 `CPropExchange` eine Basisklasse verfügt nicht über.  
  
 Legt den Kontext und die Richtung der Austausch einer Eigenschaft an.  
  
 Persistenz ist der Austausch von Statusinformationen des Steuerelements, normalerweise dargestellt durch die Eigenschaften, zwischen dem Steuerelement selbst und einem Medium.  
  
 Das Framework konstruiert ein Objekt, das von abgeleiteten `CPropExchange` Wenn es benachrichtigt wird, sind Eigenschaften eines OLE-Steuerelements von geladen werden oder gespeicherten zu persistenten Speicher.  
  
 Das Framework übergibt einen Zeiger auf diese `CPropExchange` -Objekt, des Steuerelements `DoPropExchange` Funktion. Wenn Sie einen Assistenten verwendet haben, erstellen Sie die Ausgangsdateien für des Steuerelements, das Steuerelement des `DoPropExchange` Funktionsaufrufe `COleControl::DoPropExchange`. Die Basisklassenversion tauscht vordefinierten Eigenschaften des Steuerelements; Sie ändern die abgeleitete Klasse-Version, um Eigenschaften von Exchange, dass Sie dem Steuerelement hinzugefügt haben.  
  
 `CPropExchange` kann zum Serialisieren von Eigenschaften des Steuerelements oder Initialisieren der Eigenschaften eines Steuerelements nach dem Laden oder Erstellen eines Steuerelements verwendet werden. Die `ExchangeProp` und `ExchangeFontProp` Memberfunktionen der `CPropExchange` können Eigenschaften zu speichern und von einem anderen Medium zu laden.  
  
 Weitere Informationen zur Verwendung von `CPropExchange`, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPropExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp  
 Serialisiert eine Eigenschaft, die binary large Object (BLOB)-Daten gespeichert.  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `phBlob`  
 Zeiger auf eine Variable, die zeigen, in dem die Eigenschaft gespeichert wird (der Variable ist in der Regel auf ein Member einer Klasse).  
  
 `hBlobDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft von Lese- oder Schreibvorgang ausgeführt, je nach Bedarf die Variable verweist, zu `phBlob`. Wenn `hBlobDefault` angegeben wird, sondern wird als Standardwert für die Eigenschaft verwendet werden. Dieser Wert wird verwendet, wenn die Serialisierung des Steuerelements aus irgendeinem Grund fehlschlägt.  
  
 Die Funktionen **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, und **CPropsetPropExchange::ExchangeBlobProp** außer Kraft setzen Diese rein virtuelle Funktion.  
  
##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp  
 Tauscht eine Schriftarteigenschaft zwischen einem Speichermedium und das Steuerelement an.  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `font`  
 Ein Verweis auf eine [CFontHolder](../../mfc/reference/cfontholder-class.md) Objekt, das die Schriftarteigenschaft enthält.  
  
 `pFontDesc`  
 Ein Zeiger auf eine [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) Struktur, die Werte für die Initialisierung der Standardzustand der Font-Eigenschaft bei `pFontDispAmbient` ist **NULL**.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart zum Initialisieren der Standardzustand der Font-Eigenschaft verwendet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schriftarteigenschaft Medium für das Steuerelement geladen wird, werden Schriftmerkmale Medium abgerufen und die `CFontHolder` Objekt verweist `font` wird initialisiert, indem Sie sie. Wenn die Schriftarteigenschaft gespeichert wird, werden die Eigenschaften in der Schriftartobjekt an das Medium geschrieben.  
  
 Die Funktionen **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, und **CPropsetPropExchange::ExchangeFontProp** außer Kraft setzen Diese rein virtuelle Funktion.  
  
##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp  
 Tauscht eine Eigenschaft zwischen dem Steuerelement und einer Datei an.  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `ppUnk`  
 Ein Zeiger auf eine Variable, die einen Zeiger auf der Eigenschaft enthält **IUnknown** -Schnittstelle (diese Variable in der Regel ist ein Member der Klasse).  
  
 `iid`  
 Schnittstellen-ID, der die Schnittstelle für die Eigenschaft, die das Steuerelement verwendet wird.  
  
 `pUnkDefault`  
 Der Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft für das Steuerelement aus der Datei geladen wird, wird die Eigenschaft erstellt und initialisiert, die aus der Datei. Wenn die Eigenschaft gespeichert ist, wird der Wert in die Datei geschrieben.  
  
 Die Funktionen **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, und **CPropsetPropExchange::ExchangePersistentProp** überschreiben diese rein virtuelle Funktion.  
  
##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp  
 Tauscht eine Eigenschaft zwischen einem Speichermedium und das Steuerelement an.  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>Parameter  
 `pszPropName`  
 Der Name der Eigenschaft, die ausgetauscht werden.  
  
 `vtProp`  
 Ein Symbol, den Typ der Eigenschaft, die ausgetauscht werden. Dabei sind folgende Werte möglich:  
  
|Symbol|Eigenschaftentyp|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 Ein Zeiger auf den Wert der Eigenschaft.  
  
 *pvDefault*  
 Zeiger auf einen Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft aus dem Medium für das Steuerelement geladen, wird der Wert der Eigenschaft Medium abgerufen und in das Objekt verweist gespeichert `pvProp`. Wenn die Eigenschaft auf dem Medium gespeichert wird, der Wert des Objekts verweist `pvProp` an das Medium geschrieben wird.  
  
 Die Funktionen **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, und **CPropsetPropExchange::ExchangeProp** diesem reinen Außerkraftsetzung virtuelle Funktion.  
  
##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion  
 Vom Framework aufgerufen, Persistenz von eine Versionsnummer zu behandeln.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Parameter  
 *dwVersionLoaded*  
 Verweis auf eine Variable, die die Versionsnummer der persistenten Daten geladen wird, in dem gespeichert werden.  
  
 `dwVersionDefault`  
 Die aktuelle Versionsnummer des Steuerelements.  
  
 `bConvert`  
 Gibt an, ob Daten in der aktuellen Version konvertieren oder behalten sie die gleiche Version, die geladen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
##  <a name="getversion"></a>  CPropExchange::GetVersion  
 Mit dieser Funktion wird zum Abrufen der Anzahl der Version des Steuerelements.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Versionsnummer des Steuerelements.  
  
##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous  
 Bestimmt, ob die Eigenschaft Nachrichtenaustausch asynchron ausgeführt werden.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true", wenn Eigenschaften sind ausgetauscht asynchron ausgeführt wird, andernfalls "false".  
  
##  <a name="isloading"></a>  CPropExchange::IsLoading  
 Mit dieser Funktion können Sie bestimmen, ob die Eigenschaften werden geladen, um das Steuerelement oder von ihm gespeichert.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Eigenschaften geladen werden; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)



