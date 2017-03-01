---
title: CD2DPathGeometry-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DPathGeometry
- CD2DPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry class
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
caps.latest.revision: 17
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
ms.openlocfilehash: 1c1158e55bf12d44f34896dd6752c9b8706db636
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry-Klasse
Ein Wrapper für ID2D1PathGeometry.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Erstellt ein CD2DPathGeometry-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle für das Objekt|  
|[CD2DPathGeometry::Create](#create)|Erstellt einen CD2DPathGeometry. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DPathGeometry::Destroy](#destroy)|Zerstört ein CD2DPathGeometry-Objekt. (Überschreibt [CD2DGeometry:: Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|  
|[CD2DPathGeometry::Detach](#detach)|Ressourcenschnittstelle aus dem Objekt trennt|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Ruft die Anzahl der Zahlen in der Pfadgeometrie ab.|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Ruft die Anzahl der Segmente in der Pfadgeometrie ab.|  
|[CD2DPathGeometry::Open](#open)|Ruft die Geometriesenke, die zum Auffüllen der Pfadgeometrie mit Formen und Segmente verwendet wird.|  
|[CD2DPathGeometry::Stream](#stream)|Kopiert den Inhalt der Pfadgeometrie an den angegebenen ID2D1GeometrySink.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Ein Zeiger auf eine ID2D1PathGeometry.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="a-nameattacha--cd2dpathgeometryattach"></a><a name="attach"></a>CD2DPathGeometry::Attach  
 Hängt die vorhandene Ressourcenschnittstelle für das Objekt  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="a-namecd2dpathgeometrya--cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a>CD2DPathGeometry::CD2DPathGeometry  
 Erstellt ein CD2DPathGeometry-Objekt.  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderingziel.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="a-namecreatea--cd2dpathgeometrycreate"></a><a name="create"></a>CD2DPathGeometry::Create  
 Erstellt einen CD2DPathGeometry.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderingziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="a-namedestroya--cd2dpathgeometrydestroy"></a><a name="destroy"></a>CD2DPathGeometry::Destroy  
 Zerstört ein CD2DPathGeometry-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dpathgeometrydetach"></a><a name="detach"></a>CD2DPathGeometry::Detach  
 Ressourcenschnittstelle aus dem Objekt trennt  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Ressourcenschnittstelle.  
  
##  <a name="a-namegetfigurecounta--cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a>CD2DPathGeometry::GetFigureCount  
 Ruft die Anzahl der Zahlen in der Pfadgeometrie ab.  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Zahlen in der Pfadgeometrie zurück.  
  
##  <a name="a-namegetsegmentcounta--cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a>CD2DPathGeometry::GetSegmentCount  
 Ruft die Anzahl der Segmente in der Pfadgeometrie ab.  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Segmente in der Pfadgeometrie zurück.  
  
##  <a name="a-namemppathgeometrya--cd2dpathgeometrymppathgeometry"></a><a name="m_ppathgeometry"></a>CD2DPathGeometry::m_pPathGeometry  
 Ein Zeiger auf eine ID2D1PathGeometry.  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="a-nameopena--cd2dpathgeometryopen"></a><a name="open"></a>CD2DPathGeometry::Open  
 Ruft die Geometriesenke, die zum Auffüllen der Pfadgeometrie mit Formen und Segmente verwendet wird.  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die ID2D1GeometrySink, die zum Auffüllen der Pfadgeometrie mit Formen und Segmente verwendet wird.  
  
##  <a name="a-namestreama--cd2dpathgeometrystream"></a><a name="stream"></a>CD2DPathGeometry::Stream  
 Kopiert den Inhalt der Pfadgeometrie an den angegebenen ID2D1GeometrySink.  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>Parameter  
 `geometrySink`  
 Die Senke, die der Pfadgeometrie Inhalt kopiert werden. Ändern diese Senke ändert nicht den Inhalt dieser Pfadgeometrie.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

