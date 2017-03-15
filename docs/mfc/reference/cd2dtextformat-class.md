---
title: CD2DTextFormat-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DTextFormat
- CD2DTextFormat
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextFormat class
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: 16
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f7347dbbad8290bfdc800cbacaf21400583a392
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dtextformat-class"></a>CD2DTextFormat-Klasse
Ein Wrapper für "IDWriteTextFormat".  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](#cd2dtextformat)|Erstellt ein CD2DTextFormat-Objekt.|  
|[CD2DTextFormat:: ~ CD2DTextFormat](#cd2dtextformat__~cd2dtextformat)|Der Destruktor. Wird aufgerufen, wenn ein D2D-Textformatobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextFormat::Create](#create)|Erstellt einen CD2DTextFormat. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextFormat::Destroy](#destroy)|Zerstört ein CD2DTextFormat-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextFormat::Get](#get)|Gibt die IDWriteTextFormat-Schnittstelle|  
|[CD2DTextFormat::GetFontFamilyName](#getfontfamilyname)|Ruft eine Kopie der Namen der Schriftfamilie ab.|  
|[CD2DTextFormat::GetLocaleName](#getlocalename)|Ruft eine Kopie des Gebietsschemanamens ab.|  
|[CD2DTextFormat::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextFormat::ReCreate](#recreate)|Ein CD2DTextFormat erstellt neu. (Überschreibt [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextFormat::Operator IDWriteTextFormat *](#operator_idwritetextformat_star)|Gibt die IDWriteTextFormat-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextFormat::m_pTextFormat](#m_ptextformat)|Ein Zeiger auf ein IDWriteTextFormat.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dtextformata--cd2dtextformatcd2dtextformat"></a><a name="_dtorcd2dtextformat"></a>CD2DTextFormat:: ~ CD2DTextFormat  
 Der Destruktor. Wird aufgerufen, wenn ein D2D-Textformatobjekt zerstört wird.  
  
```  
virtual ~CD2DTextFormat();
```  
  
##  <a name="a-namecd2dtextformata--cd2dtextformatcd2dtextformat"></a><a name="cd2dtextformat"></a>CD2DTextFormat::CD2DTextFormat  
 Erstellt ein CD2DTextFormat-Objekt.  
  
```  
CD2DTextFormat(
    CRenderTarget* pParentTarget,  
    const CString& strFontFamilyName,  
    FLOAT fontSize,  
    DWRITE_FONT_WEIGHT fontWeight = DWRITE_FONT_WEIGHT_NORMAL,  
    DWRITE_FONT_STYLE fontStyle = DWRITE_FONT_STYLE_NORMAL,  
    DWRITE_FONT_STRETCH fontStretch = DWRITE_FONT_STRETCH_NORMAL,  
    const CString& strFontLocale = _T(""),  
    IDWriteFontCollection* pFontCollection = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `strFontFamilyName`  
 Ein CString-Objekt, das den Namen der Schriftfamilie enthält.  
  
 `fontSize`  
 Die logische Größe der Schriftart in DIP ("geräteunabhängige Pixel")-Einheiten. Ein DIP entspricht 1/96 Zoll.  
  
 `fontWeight`  
 Ein Wert, der die Schriftbreite für das Textobjekt angibt.  
  
 `fontStyle`  
 Ein Wert, der den Schriftschnitt für das Textobjekt angibt.  
  
 `fontStretch`  
 Ein Wert, der die Font-Stretch für das Textobjekt angibt.  
  
 `strFontLocale`  
 Ein CString-Objekt, das den Gebietsschemanamen enthält.  
  
 `pFontCollection`  
 Ein Zeiger auf ein Auflistungsobjekt Schriftart. Wenn NULL ist, gibt die systemschriftsammlung an.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="a-namecreatea--cd2dtextformatcreate"></a><a name="create"></a>CD2DTextFormat::Create  
 Erstellt einen CD2DTextFormat.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-namedestroya--cd2dtextformatdestroy"></a><a name="destroy"></a>CD2DTextFormat::Destroy  
 Zerstört ein CD2DTextFormat-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namegeta--cd2dtextformatget"></a><a name="get"></a>CD2DTextFormat::Get  
 Gibt die IDWriteTextFormat-Schnittstelle  
  
```  
IDWriteTextFormat* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine IDWriteTextFormat-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namegetfontfamilynamea--cd2dtextformatgetfontfamilyname"></a><a name="getfontfamilyname"></a>CD2DTextFormat::GetFontFamilyName  
 Ruft eine Kopie der Namen der Schriftfamilie ab.  
  
```  
CString GetFontFamilyName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 CString-Objekt, das den aktuellen Schriftfamiliennamen enthält.  
  
##  <a name="a-namegetlocalenamea--cd2dtextformatgetlocalename"></a><a name="getlocalename"></a>CD2DTextFormat::GetLocaleName  
 Ruft eine Kopie des Gebietsschemanamens ab.  
  
```  
CString GetLocaleName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 CString-Objekt, das den aktuellen Gebietsschemanamen enthält.  
  
##  <a name="a-nameisvalida--cd2dtextformatisvalid"></a><a name="isvalid"></a>CD2DTextFormat::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls FALSE.  
  
##  <a name="a-namemptextformata--cd2dtextformatmptextformat"></a><a name="m_ptextformat"></a>CD2DTextFormat::m_pTextFormat  
 Ein Zeiger auf ein IDWriteTextFormat.  
  
```  
IDWriteTextFormat* m_pTextFormat;  
```  
  
##  <a name="a-nameoperatoridwritetextformatstara--cd2dtextformatoperator-idwritetextformat"></a><a name="operator_idwritetextformat_star"></a>CD2DTextFormat::Operator IDWriteTextFormat *  
 Gibt die IDWriteTextFormat-Schnittstelle  
  
```  
operator IDWriteTextFormat*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine IDWriteTextFormat-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="a-namerecreatea--cd2dtextformatrecreate"></a><a name="recreate"></a>CD2DTextFormat::ReCreate  
 Ein CD2DTextFormat erstellt neu.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

