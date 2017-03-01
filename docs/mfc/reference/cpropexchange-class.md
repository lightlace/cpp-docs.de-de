---
title: CPropExchange Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropExchange
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange class
- OLE controls, persistence
- controls [MFC], OLE
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 655d8e2f074c3bd12b1b52ece74efb844c7a9904
ms.lasthandoff: 02/24/2017

---
# <a name="cpropexchange-class"></a>CPropExchange-Klasse
Unterstützt die Implementierung der Dauerhaftigkeit für die OLE-Steuerelemente.  
  
## <a name="syntax"></a>Syntax  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Tauscht eine binary large Object (BLOB)-Eigenschaft.|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Tauscht eine Font-Eigenschaft.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Tauscht eine Eigenschaft zwischen einem Steuerelement und einer Datei.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Tauscht die Eigenschaften eines integrierten Typs.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|Tauscht die Versionsnummer eines OLE-Steuerelements.|  
|[CPropExchange::GetVersion](#getversion)|Ruft die Versionsnummer eines OLE-Steuerelements ab.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Bestimmt, ob die Eigenschaft Nachrichtenaustausch asynchron ausgeführt werden.|  
|[CPropExchange::IsLoading](#isloading)|Gibt an, ob die Eigenschaften werden in das Steuerelement geladen, oder es gespeichert.|  
  
## <a name="remarks"></a>Hinweise  
 `CPropExchange`eine Basisklasse keinen.  
  
 Legt den Kontext und die Richtung der Austausch einer Eigenschaft.  
  
 Persistenz ist der Austausch von Statusinformationen des Steuerelements, normalerweise dargestellt durch seine Eigenschaften an, zwischen dem Steuerelement selbst und einem Medium.  
  
 Das Framework konstruiert ein Objekt, das von abgeleiteten `CPropExchange` Wenn sie darüber benachrichtigt wird, dass ein OLE-Steuerelement-Eigenschaften aus geladen werden oder gespeicherten zu permanenten Speicher.  
  
 Das Framework übergibt einen Zeiger auf das `CPropExchange` -Objekt, des Steuerelements `DoPropExchange` Funktion. Wenn Sie einen Assistenten verwendet, um die Startdateien für des Steuerelements, das Steuerelement des `DoPropExchange` Funktionsaufrufe `COleControl::DoPropExchange`. Die Basisklassenversion tauscht Basiseigenschaften des Steuerelements; Ändern Sie die abgeleitete Klasse Version zu Exchange-Eigenschaften, dass Sie dem Steuerelement hinzugefügt haben.  
  
 `CPropExchange`kann verwendet werden, der Eigenschaften eines Steuerelements zu serialisieren oder Initialisieren der Eigenschaften eines Steuerelements nach dem Laden oder Erstellen eines Steuerelements. Die `ExchangeProp` und `ExchangeFontProp` Memberfunktionen der `CPropExchange` können Eigenschaften zu speichern und Laden Sie diese von anderen Medien.  
  
 Weitere Informationen zur Verwendung von `CPropExchange`, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CPropExchange`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxctl.h  
  
##  <a name="a-nameexchangeblobpropa--cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 Serialisiert eine Eigenschaft, die binary large Object (BLOB)-Daten speichert.  
  
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
 Zeiger auf eine Variable, die zeigen, in dem die Eigenschaft gespeichert wird (Variable ist in der Regel ein Member der Klasse).  
  
 `hBlobDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der Eigenschaft gelesen oder geschrieben, je nach Bedarf die Variable, auf die verwiesen wird, zu `phBlob`. Wenn `hBlobDefault` angegeben wird, wird es als Standardwert der Eigenschaft verwendet. Dieser Wert wird verwendet, wenn die Steuerung der Serialisierung aus irgendeinem Grund fehlschlägt.  
  
 Die Funktionen **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, und **CPropsetPropExchange::ExchangeBlobProp** überschreiben diese rein virtuelle Funktion.  
  
##  <a name="a-nameexchangefontpropa--cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 Tauscht zwischen einem Speichermedium und dem Steuerelement eine Font-Eigenschaft.  
  
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
 Ein Verweis auf eine [CFontHolder](../../mfc/reference/cfontholder-class.md) -Objekt, das die Font-Eigenschaft enthält.  
  
 `pFontDesc`  
 Ein Zeiger auf eine [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) Struktur, die Werte für die Initialisierung des Standardzustand für die Schriftarteigenschaft bei `pFontDispAmbient` ist **NULL**.  
  
 `pFontDispAmbient`  
 Ein Zeiger auf die **IFontDisp** Schnittstelle einer Schriftart für den Standardzustand der Font-Eigenschaft zu initialisieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schriftarteigenschaft Medium für das Steuerelement geladen wird, werden Schriftmerkmale Medium abgerufen und die `CFontHolder` Objekt, auf `font` mit ihnen initialisiert wird. Wenn die Font-Eigenschaft gespeichert wird, werden die Eigenschaften in das Font-Objekt auf das Medium geschrieben.  
  
 Die Funktionen **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, und **CPropsetPropExchange::ExchangeFontProp** überschreiben diese rein virtuelle Funktion.  
  
##  <a name="a-nameexchangepersistentpropa--cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 Tauscht eine Eigenschaft zwischen dem Steuerelement und eine Datei.  
  
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
 Ein Zeiger auf eine Variable mit einem Zeiger auf die Eigenschaft **IUnknown** Schnittstelle (diese Variable ist in der Regel ein Member der Klasse).  
  
 `iid`  
 Schnittstellen-ID der Schnittstelle für die Eigenschaft, die das Steuerelement verwenden.  
  
 `pUnkDefault`  
 Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft für das Steuerelement aus der Datei geladen wird, wird die Eigenschaft erstellt und initialisiert, aus der Datei. Wenn die Eigenschaft gespeichert wird, wird der Wert in die Datei geschrieben.  
  
 Die Funktionen **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, und **CPropsetPropExchange::ExchangePersistentProp** überschreiben diese rein virtuelle Funktion.  
  
##  <a name="a-nameexchangepropa--cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 Tauscht eine Eigenschaft zwischen einem Speichermedium und dem Steuerelement.  
  
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
 Ein Symbol, die den Typ der Eigenschaft, die ausgetauscht werden. Dabei sind folgende Werte möglich:  
  
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
 Ein Zeiger auf einen Standardwert für die Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Austausch erfolgreich war; 0, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Eigenschaft zum Steuerelement Medium geladen wird, wird der Wert der Eigenschaft Medium abgerufen und in das Objekt, das auf gespeichert `pvProp`. Wenn die Eigenschaft auf dem Medium gespeichert wird, der Wert des Objekts auf den `pvProp` auf das Medium geschrieben.  
  
 Die Funktionen **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, und **CPropsetPropExchange::ExchangeProp** überschreiben diese rein virtuelle Funktion.  
  
##  <a name="a-nameexchangeversiona--cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 Vom Framework aufgerufen, Persistenz einer Versionsnummer zu behandeln.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Parameter  
 *dwVersionLoaded*  
 Verweis auf eine Variable, die Versionsnummer der geladenen permanenten Daten gespeichert wird.  
  
 `dwVersionDefault`  
 Die aktuelle Versionsnummer des Steuerelements.  
  
 `bConvert`  
 Gibt an, ob Daten dauerhafte auf die aktuelle Version zu konvertieren, oder behalten sie die gleiche Version, die geladen wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
##  <a name="a-namegetversiona--cpropexchangegetversion"></a><a name="getversion"></a>CPropExchange::GetVersion  
 Rufen Sie diese Funktion, um die Versionsnummer des Steuerelements abzurufen.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Versionsnummer des Steuerelements.  
  
##  <a name="a-nameisasynchronousa--cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 Bestimmt, ob die Eigenschaft Nachrichtenaustausch asynchron ausgeführt werden.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True, wenn Eigenschaften sind ausgetauscht asynchron ist, andernfalls FALSE.  
  
##  <a name="a-nameisloadinga--cpropexchangeisloading"></a><a name="isloading"></a>CPropExchange::IsLoading  
 Rufen Sie diese Funktion, um festzustellen, ob die Eigenschaften werden auf das Steuerelement geladen oder daraus gespeichert.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Eigenschaften geladen werden; andernfalls 0.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControl:: DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)




