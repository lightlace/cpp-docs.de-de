---
title: ATL_DRAWINFO Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: bc124de97acf85d6e706605afb55b0747a327ade
ms.lasthandoff: 02/24/2017

---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO-Struktur
Enthält Informationen zum Rendern an verschiedene Ziele, z. B. ein Drucker, ein Metadatei oder ActiveX-Steuerelement verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ATL_DRAWINFO {
    UINT cbSize;
    DWORD dwDrawAspect;
    LONG lindex;
    DVTARGETDEVICE* ptd;
    HDC hicTargetDev;
    HDC hdcDraw;
    LPCRECTL prcBounds;
    LPCRECTL prcWBounds;
    BOOL bOptimize;
    BOOL bZoomed;
    BOOL bRectInHimetric;
    SIZEL ZoomNum;
    SIZEL ZoomDen;
};
```  
  
## <a name="members"></a>Mitglieder  
 `cbSize`  
 Die Größe der Struktur in Bytes.  
  
 **dwDrawAspect**  
 Gibt an, wie das Ziel dargestellt werden soll. Darstellungen können Inhalte, ein Symbol, eine Miniaturansicht oder einem gedruckten Dokument enthalten. Eine Liste der möglichen Werte finden Sie unter [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) und [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **lindex**  
 Teil des Ziels, der für den Ziehvorgang relevant ist. Die Interpretation hängt vom Wert in der **DwDrawAspect** Element.  
  
 **ptd**  
 Zeiger auf eine [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) -Struktur, die abhängig vom angegebenen Aspekt zeichnen Optimierungen ermöglicht. Beachten Sie, dass neuere Objekte und Container, die optimierte Zeichnung Schnittstellen unterstützen auch diese Member unterstützen. Angeben von älteren Objekten und Containern, die nicht optimierte zeichnen Schnittstellen immer **NULL** für dieses Element.  
  
 **hicTargetDev**  
 Der Informationskontext für das Zielgerät auf den **Ptd** aus dem das Objekt Gerätemetrik abrufen und Funktionen des Geräts prüfen kann. Wenn **Ptd** ist **NULL**, das Objekt sollte ignoriert den Wert in der **HicTargetDev** Element.  
  
 **hdcDraw**  
 Der Gerätekontext, auf denen gezeichnet werden soll. Für ein fensterloses-Objekt das **HdcDraw** ist Mitglied der `MM_TEXT` Zuordnungsmodus mit ihren logischen Koordinaten entsprechen der Clientkoordinaten des enthaltenden Fensters. Darüber hinaus sollte der Gerätekontext im selben Zustand wie der in der Regel durch Übergeben einer `WM_PAINT` Nachricht.  
  
 **prcBounds**  
 Zeiger auf eine [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) -Struktur und gibt das Rechteck auf **HdcDraw** und in dem das Objekt gezeichnet werden soll. Dieses Element steuert die Positionierung und Dehnen von des Objekts. Dieser Member sollte **NULL** ein fensterloses aktive in-Place-Objekt zu zeichnen. In jedem anderen Fall **NULL** ist kein gültiger Wert und führt eine `E_INVALIDARG` Fehlercode. Wenn der Container nicht erfolgreich**NULL** Wert, der eine fensterlose Objekt, das den angeforderten Aspekt in den angegebenen Gerätekontext und das Rechteck Rendern muss. Ein Container kann diese aus einem fensterlose-Objekt zum Rendern einer zweiten, nicht aktive Ansicht des Objekts oder zum Drucken des Objekts anfordern.  
  
 **prcWBounds**  
 Wenn **HdcDraw** ist ein Metadatei-Gerätekontext (finden Sie unter [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]), dies ist ein Zeiger auf eine **RECTL** -Struktur, die das umschließende Rechteck in der zugrunde liegenden Metadatei angibt. Rectangle-Struktur enthält das Fenster Umfang und der Ursprungspunkt des Fensters. Diese Werte sind hilfreich für das Zeichnen von Metadateien. Das Rechteck erkennbar **PrcBounds** in diese geschachtelt ist **PrcWBounds** Rechteck; sie sind in denselben Koordinatenraum.  
  
 **bOptimize**  
 Ungleich NULL ist, ist das Zeichnen des Steuerelements werden optimiert, andernfalls 0. Wenn das Zeichnen optimiert ist, wird der Zustand des Gerätekontexts automatisch wiederhergestellt, wenn Sie fertig sind rendern.  
  
 **bZoomed**  
 Wert ungleich NULL, wenn das Ziel einen Zoomfaktor, andernfalls 0 verfügt. Der Zoomfaktor befindet sich in **ZoomNum**.  
  
 **bRectInHimetric**  
 Einen Wert ungleich NULL die Dimensionen des **PrcBounds** befinden sich im **HIMETRIC**, andernfalls 0.  
  
 **ZoomNum**  
 Die Breite und Höhe des Rechtecks, in dem das Objekt gerendert wird. Der Zoomfaktor entlang der x-Achse (der Anteil der natürlichen Größe des Objekts, in seiner aktuellen Ausdehnung) des Ziels ist der Wert der **ZoomNum.cx** geteilt durch den Wert der **ZoomDen.cx**. Der Zoomfaktor entlang der y-Achse wird auf ähnliche Weise erreicht.  
  
 **ZoomDen**  
 Die tatsächliche Breite und Höhe des Ziels.  
  
## <a name="remarks"></a>Hinweise  
 Typisch für diese Struktur wäre das Abrufen von Informationen bei der Wiedergabe des Zielobjekts. Angenommen, Sie Werte abrufen können `ATL_DRAWINFO` innerhalb der Überladung der [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).  
  
 Diese Struktur speichert relevante Informationen verwendet, um die Darstellung eines Objekts für das Zielgerät zu rendern. Die bereitgestellten Informationen kann in der Zeichnung auf dem Bildschirm, einen Drucker oder sogar eine Metadatei verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)






