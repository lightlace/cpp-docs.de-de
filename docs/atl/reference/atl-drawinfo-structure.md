---
title: ATL_DRAWINFO Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATL::ATL_DRAWINFO
- ATL_DRAWINFO
- ATL.ATL_DRAWINFO
dev_langs:
- C++
helpviewer_keywords:
- ATL_DRAWINFO structure
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c8ba7be259a10ee1bf47bbdc401a2389adac2be
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34255963"
---
# <a name="atldrawinfo-structure"></a>ATL_DRAWINFO-Struktur
Enthält Informationen zum Rendern an verschiedene Ziele, wie Drucker, Metadatei oder ActiveX-Steuerelement verwendet.  
  
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
  
## <a name="members"></a>Member  
 `cbSize`  
 Die Größe der Struktur, in Bytes.  
  
 **dwDrawAspect**  
 Gibt an, wie das Ziel dargestellt werden soll. Darstellungen können Inhalte, ein Symbol, eine Miniaturansicht oder einem gedruckten Dokument enthalten. Eine Liste der möglichen Werte finden Sie unter [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) und [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **lindex**  
 Teil des Ziels, das für den Ziehvorgang relevant ist. Die Interpretation hängt vom Wert in der **DwDrawAspect** Member.  
  
 **ptd**  
 Zeiger auf eine [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) -Struktur, die abhängig vom angegebenen Aspekt zeichnen Optimierungen ermöglicht. Beachten Sie, dass neuere Objekten und Containern, die die optimierte zeichnen Schnittstellen unterstützen auch bei diesem Member unterstützen. Angeben von älteren Objekten und Containern, die nicht optimierte zeichnen Schnittstellen immer unterstützen **NULL** für diesen Member.  
  
 **hicTargetDev**  
 Der Informationskontext für das Zielgerät verweist **Ptd** aus dem das Objekt Gerätemetrik abrufen kann, und Testen Sie die Funktionen des Geräts. Wenn **Ptd** ist **NULL**, das Objekt sollte den Wert im ignorieren der **HicTargetDev** Member.  
  
 **hdcDraw**  
 Der Gerätekontext, auf dem gezeichnet werden soll. Für ein fensterlose-Objekt das **HdcDraw** ist Mitglied der `MM_TEXT` Zuordnungsmodus mit ihren logischen Koordinaten Abgleich der Clientkoordinaten des enthaltenden Fensters. Darüber hinaus muss der Gerätekontext im gleichen Zustand wie normalerweise durch Übergeben einer `WM_PAINT` Nachricht.  
  
 **prcBounds**  
 Zeiger auf eine [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907) Struktur, die das Rechteck angibt, auf **HdcDraw** und in dem das Objekt gezeichnet werden soll. Bei diesem Member steuert die Positionierung und Dehnen des Objekts. Bei diesem Member muss **NULL** ein fensterloses direktes aktives Objekt gezeichnet werden soll. In jedem Fall **NULL** ist kein gültiger Wert und sollten dazu führen, ein `E_INVALIDARG` Fehlercode. Wenn der Container nicht erfolgreich**NULL** Wert mit einem fensterlose Objekt, das Objekt sollte den angeforderten Aspekt gerendert, in den angegebenen Gerätekontext und das Rechteck. Ein Container kann dies von einem fensterlose Objekt zum Rendern einer Ansicht inaktiven Zweitens des Objekts oder zum Drucken des Objekts anfordern.  
  
 **prcWBounds**  
 Wenn **HdcDraw** ist ein Metadatei Gerätekontext (finden Sie unter [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) im Windows SDK), dies ist ein Zeiger auf eine **RECTL** Struktur, die das umschließende Rechteck in angibt der zugrunde liegenden Metadatei. Die Rechteckstruktur enthält die Fenster Umfang und den Fensterursprung an. Diese Werte sind hilfreich für das Zeichnen von Metadateien. Das Rechteck erkennbar **PrcBounds** in diese geschachtelt ist **PrcWBounds** Rechteck; sie befinden sich in der gleichen Koordinatenbereich.  
  
 **bOptimize**  
 Wert ungleich NULL, wenn das Zeichnen des Steuerelements ist, werden optimiert, andernfalls 0. Wenn die Zeichnung optimiert ist, wird der Status des Gerätekontexts automatisch wiederhergestellt, wenn Sie fertig sind rendern.  
  
 **bZoomed**  
 Wert ungleich NULL, wenn das Ziel ein Zoom-Faktors, andernfalls 0 hat. Der Zoomfaktor wird gespeichert, **ZoomNum**.  
  
 **bRectInHimetric**  
 Einen Wert ungleich NULL die Dimensionen der **PrcBounds** befinden sich im **HIMETRIC**, andernfalls 0.  
  
 **ZoomNum**  
 Die Breite und Höhe des Rechtecks, in dem das Objekt gerendert wird. Der Zoomfaktor entlang der x-Achse (das Größenverhältnis der natürlichen Objektgröße auf seine aktuellen Block) des Ziels ist der Wert der **ZoomNum.cx** geteilt durch den Wert der **ZoomDen.cx**. Der Zoomfaktor entlang der y-Achse erfolgt auf ähnliche Weise.  
  
 **ZoomDen**  
 Die tatsächliche Breite und Höhe des Ziels.  
  
## <a name="remarks"></a>Hinweise  
 Typische Verwendung dieser Struktur wäre das Abrufen von Informationen bei der Wiedergabe des Zielobjekts. Beispielsweise konnten Sie abrufen, Werte aus `ATL_DRAWINFO` innerhalb der Überladung der [CComControlBase::OnDrawAdvanced](ccomcontrolbase-class.md#ondrawadvanced).  
  
 Diese Struktur speichert enthaltenen wichtigen Informationen verwendet, um die Darstellung eines Objekts für das Zielgerät gerendert. Die bereitgestellten Informationen kann in Zeichnen auf dem Bildschirm, einen Drucker oder sogar eine Metadatei verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlctl.h  
  
## <a name="see-also"></a>Siehe auch  
  [Klassen und Strukturen](../../atl/reference/atl-classes.md) [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../../atl/reference/ccomcontrolbase-class.md#ondrawadvanced)





