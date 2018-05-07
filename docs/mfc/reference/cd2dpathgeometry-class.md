---
title: CD2DPathGeometry-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
dev_langs:
- C++
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a3afe8efa5730c3ef0f4448b1c548724b56b7cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry-Klasse
Ein Wrapper für ID2D1PathGeometry.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CD2DPathGeometry : public CD2DGeometry;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::CD2DPathGeometry](#cd2dpathgeometry)|Erstellt ein CD2DPathGeometry-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::Attach](#attach)|Hängt die vorhandene Ressourcenschnittstelle, um das Objekt|  
|[CD2DPathGeometry::Create](#create)|Erstellt einen CD2DPathGeometry. (Überschreibt [CD2DResource:: Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DPathGeometry::Destroy](#destroy)|Zerstört ein CD2DPathGeometry-Objekt. (Überschreibt [CD2DGeometry:: Destroy](../../mfc/reference/cd2dgeometry-class.md#destroy).)|  
|[CD2DPathGeometry::Detach](#detach)|Trennt Ressourcenschnittstelle aus dem Objekt|  
|[CD2DPathGeometry::GetFigureCount](#getfigurecount)|Ruft die Anzahl der Zahlen in der Pfadgeometrie ab.|  
|[CD2DPathGeometry::GetSegmentCount](#getsegmentcount)|Ruft die Anzahl der Segmente in der Pfadgeometrie ab.|  
|[CD2DPathGeometry::Open](#open)|Ruft die Geometrie-Ereignissenke, die zum Auffüllen der Pfadgeometrie mit Abbildungen und Segmente verwendet wird.|  
|[CD2DPathGeometry::Stream](#stream)|Kopiert den Inhalt der Pfadgeometrie auf den angegebenen ID2D1GeometrySink an.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CD2DPathGeometry::m_pPathGeometry](#m_ppathgeometry)|Ein Zeiger auf eine ID2D1PathGeometry.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
 `CD2DPathGeometry`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="attach"></a>  CD2DPathGeometry::Attach  
 Hängt die vorhandene Ressourcenschnittstelle, um das Objekt  
  
```  
void Attach(ID2D1PathGeometry* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Vorhandene Ressourcenschnittstelle. NULL darf nicht sein  
  
##  <a name="cd2dpathgeometry"></a>  CD2DPathGeometry::CD2DPathGeometry  
 Erstellt ein CD2DPathGeometry-Objekt.  
  
```  
CD2DPathGeometry(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentTarget`  
 Ein Zeiger auf das Renderziel.  
  
 `bAutoDestroy`  
 Gibt an, dass das Objekt vom Besitzer (pParentTarget) zerstört wird.  
  
##  <a name="create"></a>  CD2DPathGeometry::Create  
 Erstellt einen CD2DPathGeometry.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Ein Zeiger auf das Renderziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="destroy"></a>  CD2DPathGeometry::Destroy  
 Zerstört ein CD2DPathGeometry-Objekt.  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>  CD2DPathGeometry::Detach  
 Trennt Ressourcenschnittstelle aus dem Objekt  
  
```  
ID2D1PathGeometry* Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Ressourcenschnittstelle.  
  
##  <a name="getfigurecount"></a>  CD2DPathGeometry::GetFigureCount  
 Ruft die Anzahl der Zahlen in der Pfadgeometrie ab.  
  
```  
int GetFigureCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Zahlen in der Pfadgeometrie zurück.  
  
##  <a name="getsegmentcount"></a>  CD2DPathGeometry::GetSegmentCount  
 Ruft die Anzahl der Segmente in der Pfadgeometrie ab.  
  
```  
int GetSegmentCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Segmente in der Pfadgeometrie zurück.  
  
##  <a name="m_ppathgeometry"></a>  CD2DPathGeometry::m_pPathGeometry  
 Ein Zeiger auf eine ID2D1PathGeometry.  
  
```  
ID2D1PathGeometry* m_pPathGeometry;  
```  
  
##  <a name="open"></a>  CD2DPathGeometry::Open  
 Ruft die Geometrie-Ereignissenke, die zum Auffüllen der Pfadgeometrie mit Abbildungen und Segmente verwendet wird.  
  
```  
ID2D1GeometrySink* Open();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die ID2D1GeometrySink, die zum Auffüllen der Pfadgeometrie mit Abbildungen und Segmente verwendet wird.  
  
##  <a name="stream"></a>  CD2DPathGeometry::Stream  
 Kopiert den Inhalt der Pfadgeometrie auf den angegebenen ID2D1GeometrySink an.  
  
```  
BOOL Stream(ID2D1GeometrySink* geometrySink);
```  
  
### <a name="parameters"></a>Parameter  
 `geometrySink`  
 Die Senke, die in der Inhalt der Pfadgeometrie kopiert werden. Ändern diese Senke ändert sich nicht auf den Inhalt dieser Pfadgeometrie aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
