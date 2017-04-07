---
title: CD2DTextLayout-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::CD2DTextLayout
- AFXRENDERTARGET/CD2DTextLayout::Create
- AFXRENDERTARGET/CD2DTextLayout::Destroy
- AFXRENDERTARGET/CD2DTextLayout::Get
- AFXRENDERTARGET/CD2DTextLayout::GetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::GetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::IsValid
- AFXRENDERTARGET/CD2DTextLayout::ReCreate
- AFXRENDERTARGET/CD2DTextLayout::SetFontFamilyName
- AFXRENDERTARGET/CD2DTextLayout::SetLocaleName
- AFXRENDERTARGET/CD2DTextLayout::m_pTextLayout
dev_langs:
- C++
helpviewer_keywords:
- CD2DTextLayout class
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
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
ms.openlocfilehash: b9d3873058613041042857b7edf213d207f058c5
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dtextlayout-class"></a>CD2DTextLayout-Klasse
Ein Wrapper für "IDWriteTextLayout".  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](#cd2dtextlayout)|Erstellt ein CD2DTextLayout-Objekt.|  
|[CD2DTextLayout:: ~ CD2DTextLayout](#cd2dtextlayout__~cd2dtextlayout)|Der Destruktor. Wird aufgerufen, wenn ein D2D TextLayout-Objekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextLayout::Create](#create)|Erstellt einen CD2DTextLayout. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DTextLayout::Destroy](#destroy)|Zerstört ein CD2DTextLayout-Objekt. (Überschreibt [CD2DResource:: Destroy](../../mfc/reference/cd2dresource-class.md#destroy).)|  
|[CD2DTextLayout::Get](#get)|Gibt die IDWriteTextLayout-Schnittstelle|  
|[CD2DTextLayout::GetFontFamilyName](#getfontfamilyname)|Kopiert den Namen der Schriftfamilie des Texts an der angegebenen Position.|  
|[CD2DTextLayout::GetLocaleName](#getlocalename)|Ruft den Gebietsschemanamen des Texts an der angegebenen Position ab.|  
|[CD2DTextLayout::IsValid](#isvalid)|Überprüft die Gültigkeit der Ressource (überschreibt [CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid).)|  
|[CD2DTextLayout::ReCreate](#recreate)|Ein CD2DTextLayout erstellt neu. (Überschreibt [CD2DResource::ReCreate](../../mfc/reference/cd2dresource-class.md#recreate).)|  
|[CD2DTextLayout::SetFontFamilyName](#setfontfamilyname)|Legt Null endenden Schriftfamiliennamen für Text innerhalb eines angegebenen Textbereichs|  
|[CD2DTextLayout::SetLocaleName](#setlocalename)|Legt den Gebietsschemanamen für Text innerhalb eines angegebenen Textbereichs fest|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextLayout::Operator IDWriteTextLayout *](#operator_idwritetextlayout_star)|Gibt die IDWriteTextLayout-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DTextLayout::m_pTextLayout](#m_ptextlayout)|Ein Zeiger auf ein IDWriteTextLayout.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcd2dtextlayout"></a>CD2DTextLayout:: ~ CD2DTextLayout  
 Der Destruktor. Wird aufgerufen, wenn ein D2D TextLayout-Objekt zerstört wird.  
  
```  
virtual ~CD2DTextLayout();
```  
  
##  <a name="cd2dtextlayout"></a>CD2DTextLayout::CD2DTextLayout  
 Erstellt ein CD2DTextLayout-Objekt.  
  
```  
CD2DTextLayout(
    CRenderTarget* pParentTarget,  
    const CString& strText,  
    CD2DTextFormat& textFormat,  
    const CD2DSizeF& sizeMax,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `strText`  
 Ein CString-Objekt, erstellen Sie ein neues CD2DTextLayout-Objekt aus der Zeichenfolge enthält.  
  
 `textFormat`  
 Ein CString-Objekt, das auf die Zeichenfolge anzuwendende Format enthält.  
  
 `sizeMax`  
 Die Größe des im Layout.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="create"></a>CD2DTextLayout::Create  
 Erstellt einen CD2DTextLayout.  
  
```  
virtual HRESULT Create(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>CD2DTextLayout::Destroy  
 Zerstört ein CD2DTextLayout-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="get"></a>CD2DTextLayout::Get  
 Gibt die IDWriteTextLayout-Schnittstelle  
  
```  
IDWriteTextLayout* Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine IDWriteTextLayout-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getfontfamilyname"></a>CD2DTextLayout::GetFontFamilyName  
 Kopiert den Namen der Schriftfamilie des Texts an der angegebenen Position.  
  
```  
CString GetFontFamilyName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `currentPosition`  
 Die Position des Texts untersuchen.  
  
 `textRange`  
 Der Textbereich mit dem gleichen Formatierung wie der Text an der mit CurrentPosition angegebenen Position. Dies bedeutet, dass die Ausführung genau dieselbe Formatierung wie die angegebene Position, einschließlich, aber nicht beschränkt auf den Namen der Schriftfamilie.  
  
### <a name="return-value"></a>Rückgabewert  
 CString-Objekt, das den aktuellen Schriftfamiliennamen enthält.  
  
##  <a name="getlocalename"></a>CD2DTextLayout::GetLocaleName  
 Ruft den Gebietsschemanamen des Texts an der angegebenen Position ab.  
  
```  
CString GetLocaleName(
    UINT32 currentPosition,  
    DWRITE_TEXT_RANGE* textRange = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `currentPosition`  
 Die Position des Texts zu überprüfen.  
  
 `textRange`  
 Der Textbereich mit dem gleichen Formatierung wie der Text an der mit CurrentPosition angegebenen Position. Dies bedeutet, dass die Ausführung genau dieselbe Formatierung wie die angegebene Position, einschließlich, aber nicht beschränkt auf den Gebietsschemanamen.  
  
### <a name="return-value"></a>Rückgabewert  
 CString-Objekt, das den aktuellen Gebietsschemanamen enthält.  
  
##  <a name="isvalid"></a>CD2DTextLayout::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls FALSE.  
  
##  <a name="m_ptextlayout"></a>CD2DTextLayout::m_pTextLayout  
 Ein Zeiger auf ein IDWriteTextLayout.  
  
```  
IDWriteTextLayout* m_pTextLayout;  
```  
  
##  <a name="operator_idwritetextlayout_star"></a>CD2DTextLayout::Operator IDWriteTextLayout *  
 Gibt die IDWriteTextLayout-Schnittstelle  
  
```  
operator IDWriteTextLayout*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine IDWriteTextLayout-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="recreate"></a>CD2DTextLayout::ReCreate  
 Ein CD2DTextLayout erstellt neu.  
  
```  
virtual HRESULT ReCreate(CRenderTarget* */);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="setfontfamilyname"></a>CD2DTextLayout::SetFontFamilyName  
 Legt Null endenden Schriftfamiliennamen für Text innerhalb eines angegebenen Textbereichs  
  
```  
BOOL SetFontFamilyName(
    LPCWSTR pwzFontFamilyName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parameter  
 `pwzFontFamilyName`  
 Den Namen der Schriftfamilie, die für die gesamte Textzeichenfolge innerhalb des von TextRange angegebenen Bereichs gilt  
  
 `textRange`  
 Textbereich, dem diese Änderung gilt  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben  
  
##  <a name="setlocalename"></a>CD2DTextLayout::SetLocaleName  
 Legt den Gebietsschemanamen für Text innerhalb eines angegebenen Textbereichs fest  
  
```  
BOOL SetLocaleName(
    LPCWSTR pwzLocaleName,  
    DWRITE_TEXT_RANGE textRange);
```  
  
### <a name="parameters"></a>Parameter  
 `pwzLocaleName`  
 Ein Gebietsschema Null-terminierte Zeichenfolge  
  
 `textRange`  
 Textbereich, dem diese Änderung gilt  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

