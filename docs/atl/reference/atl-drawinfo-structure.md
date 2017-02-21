---
title: "ATL_DRAWINFO Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::ATL_DRAWINFO"
  - "ATL_DRAWINFO"
  - "ATL.ATL_DRAWINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL_DRAWINFO structure"
ms.assetid: dd2e2aa8-e8c5-403b-b4df-35c0f6f57fb7
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# ATL_DRAWINFO Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enthält die Informationen, die zum Rendern an verschiedene Ziele, wie einem Drucker, einer Metadatei oder einem ActiveX\-Steuerelement verwendet werden.  
  
## Syntax  
  
```  
  
      struct ATL_DRAWINFO{  
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
  
## Mitglieder  
 `cbSize`  
 Die Größe der Struktur, in Bytes.  
  
 **dwDrawAspect**  
 Gibt an, wie das Ziel dargestellt werden soll.  Darstellungen können Inhalt, ein Symbol, eine Miniaturansicht oder ein gedrucktes Dokument enthalten.  Eine Liste der möglichen Werten, finden Sie unter [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) und [DVASPECT2](http://msdn.microsoft.com/library/windows/desktop/ms688644).  
  
 **lindex**  
 Teil des Ziels, das relevant für den Vorgang Videofunktionen ist.  Die Interpretation variiert je nach Wert im **dwDrawAspect**\-Member.  
  
 **ptd**  
 Zeiger auf eine [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613)\-Struktur, die Zeichnungsoptimierungen abhängig von dem angegebenen Aspekt aktiviert.  Beachten Sie, dass neuere Objekte und Container, die optimierte Zeichnungsschnittstellen unterstützen, diesen Member auch unterstützen.  Ältere Objekte und Container, die nicht optimierte Zeichnungsschnittstellen unterstützen, geben immer **NULL** für diesen Member.  
  
 **hicTargetDev**  
 Informationskontext für das Zielgerät wurde auf durch **ptd**, aus der das Objekt Gerätenmetrik extrahieren kann und testet die Features des Geräts.  Wenn **ptdNULL** ist, sollte das Objekt den Wert im **hicTargetDev**\-Member ignorieren.  
  
 **hdcDraw**  
 Klicken Sie im der Gerätekontext zu zeichnen.  Ein fensterloses Objekt ist der **hdcDraw**\-Member im `MM_TEXT` Zuordnungsmodus mit seinen logischen Koordinaten, die die Clientkoordinaten des übergeordneten Fensters übereinstimmen.  Außerdem sollte der Gerätekontext im gleichen Zustand wie der sein, der normalerweise durch eine `WM_PAINT` Meldung übergeben wird.  
  
 **prcBounds**  
 Zeiger auf eine [RECTL](http://msdn.microsoft.com/library/windows/desktop/dd162907)\-Struktur wird das Rechteck auf **hdcDraw** und, in dem das Objekt gezeichnet werden soll.  Dieser Member steuert die Positionierung und die Strecken des Objekts.  Dieser Member sollte **NULL** sein, um einen fensterlose direkt aktiven Objekts zu zeichnen.  In jeder anderen Situation **NULL** ist kein gültiger Wert und einen `E_INVALIDARG` Fehlercode führen.  Wenn der Container einen Nicht \-\-**NULL**\-Wert einem fensterlose Objekt übergibt, sollte das Objekt den angeforderten Aspekt in den angegebenen Gerätekontext und in das Rechteck rendern.  Ein Container kann dieses von einem fensterlose Objekt benötigen, um eine zweite, keine aktive Ansicht des Objekts zu rendern oder das Objekt auszugeben.  
  
 **prcWBounds**  
 Wenn **hdcDraw** ein Metadateigerätekontext \(siehe [GetDeviceCaps](http://msdn.microsoft.com/library/windows/desktop/dd144877) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\), ist, ist dies ein Zeiger auf eine Struktur **RECTL** das umschließende Rechteck in der zugrunde liegenden Metadatei angibt.  Die Rechteckstruktur enthält die Fenstergröße und den Fensterursprung.  Diese Werte sind zum Zeichnen von Metadateien hilfreich.  Das Rechteck, das durch **prcBounds** angegeben wird, wird in diesem **prcWBounds** Rechtecks geschachtelt; Sie sind im denselben Koordinatenraum.  
  
 **bOptimize**  
 Ungleich 0 \(null\), wenn die Zeichnung des Steuerelements optimiert werden soll; andernfalls 0.  Wenn die Zeichnung optimiert ist, wird der Zustand des Gerätekontexts automatisch wiederhergestellt, wenn Sie der Rendern sind.  
  
 **bZoomed**  
 Ungleich 0 \(null\), wenn das Ziel einen Zoomfaktor verfügt; andernfalls 0.  Der Zoomfaktor wird in **ZoomNum** gespeichert.  
  
 **bRectInHimetric**  
 Ungleich 0 \(null\), wenn die Dimensionen des **prcBounds** in **HIMETRIC** sind; andernfalls 0.  
  
 **ZoomNum**  
 Die Breite und Höhe des Rechtecks, in das das Objekt gerendert wird.  Der Zoomfaktor entlang der x\-Achse \(der Anteil der natürliche Größe des Objekts zu aktuellen Wertebereich\) des Ziels ist der Wert von **ZoomNum.cx** geteilt durch den Wert von **ZoomDen.cx**.  Der Zoomfaktor entlang der y\-Achse wird auf ähnliche Weise erreicht.  
  
 **ZoomDen**  
 Die tatsächliche Breite und Höhe des Ziels.  
  
## Hinweise  
 Typische Verwendung dieser Struktur würde der Abruf von Informationen beim Anzeigen des Zielobjekts sein.  Beispielsweise können Sie Werte aus `ATL_DRAWINFO` innerhalb der Überladung von [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md) abrufen.  
  
 Diese Struktur speichert die entsprechenden Informationen, die verwendet werden, um die Darstellung eines Objekts für das Zielgerät zu rendern.  Die bereitgestellten Informationen können in Zeichnungen auf dem Bildschirm, auf einem Drucker oder sogar auf eine Metadatei verwendet werden.  
  
## Anforderungen  
 **Header:** atlctl.h  
  
## Siehe auch  
 [Strukturen](../../atl/reference/atl-structures.md)   
 [IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)   
 [CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)