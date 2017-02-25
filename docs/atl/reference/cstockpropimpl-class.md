---
title: "CStockPropImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStockPropImpl"
  - "ATL::CStockPropImpl"
  - "ATL.CStockPropImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [ATL], Basiseigenschaften"
  - "CStockPropImpl class"
  - "Basiseigenschaften, ATL-Steuerelemente"
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CStockPropImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden für die Unterstützung von vordefinierten Eigenschaftswerten.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class InterfaceName,   
const IID* piid= &_ATL_IIDOF(InterfaceName),   
const GUID* plibid= &CComModule::m_libid,   
WORD wMajor= 1,  
WORD wMinor= 0,   
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE CStockPropImpl :  
public IDispatchImpl< InterfaceName, piid, plibid, wMajor,  
   wMinor, tihclass>  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die das Steuerelement implementiert und von `CStockPropImpl` abgeleitet.  
  
 `InterfaceName`  
 Eine duale Schnittstelle, die die vordefinierten Eigenschaften verfügbar macht.  
  
 `piid`  
 Ein Zeiger auf IID von `InterfaceName`.  
  
 `plibid`  
 Ein Zeiger auf LIBID der Typbibliothek, die die Definition von `InterfaceName` enthält.  
  
 `wMajor`  
 Die Hauptversion der Typbibliothek.  Der Standardwert ist 1.  
  
 `wMinor`  
 Die Nebenversion der Typbibliothek.  Der Standardwert ist 0.  
  
 `tihclass`  
 Die Klasse verwendet, um die Typinformationen für `T` zu verwalten.  Der Standardwert ist `CComTypeInfoHolder`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|||  
|-|-|  
|[get\_Appearance](../Topic/CStockPropImpl::get_Appearance.md)|Rufen Sie diese Methode auf, um das Farbenformat abzurufen, das vom Steuerelement, beispielsweise, Ebene oder 3D verwendet wird.|  
|[get\_AutoSize](../Topic/CStockPropImpl::get_AutoSize.md)|Rufen Sie diese Methode auf, um den Status des Flags abzurufen, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.|  
|[get\_BackColor](../Topic/CStockPropImpl::get_BackColor.md)|Rufen Sie diese Methode auf, um die Hintergrundfarbe des Steuerelements abzurufen.|  
|[get\_BackStyle](../Topic/CStockPropImpl::get_BackStyle.md)|Rufen Sie diese Methode auf, um das Hintergrundformat des Steuerelements abzurufen, entweder transparent oder nicht transparent.|  
|[get\_BorderColor](../Topic/CStockPropImpl::get_BorderColor.md)|Rufen Sie diese Methode auf, um die Rahmenfarbe des Steuerelements abzurufen.|  
|[get\_BorderStyle](../Topic/CStockPropImpl::get_BorderStyle.md)|Rufen Sie diese Methode auf, um die Rahmenart des Steuerelements abzurufen.|  
|[get\_BorderVisible](../Topic/CStockPropImpl::get_BorderVisible.md)|Rufen Sie diese Methode auf, um den Status des Flags abzurufen, das angibt, ob der Ränder des Steuerelements oder ausgeblendet ist.|  
|[get\_BorderWidth](../Topic/CStockPropImpl::get_BorderWidth.md)|Rufen Sie diese Methode auf, um die Breite \(in Pixel\) des Rahmens des Steuerelements abzurufen.|  
|[get\_Caption](../Topic/CStockPropImpl::get_Caption.md)|Rufen Sie diese Methode auf, um den Text abzurufen, der in der Beschriftung eines Objekts angegeben wird.|  
|[get\_DrawMode](../Topic/CStockPropImpl::get_DrawMode.md)|Rufen Sie diese Methode auf, um den Zeichnungsmodus des Steuerelements, beispielsweise, XOR\-Stift abzurufen oder Farben umzukehren.|  
|[get\_DrawStyle](../Topic/CStockPropImpl::get_DrawStyle.md)|Rufen Sie diese Methode auf, um das Zeichnungsformat des Steuerelements, den beispielsweise, Vollton\- abzurufen, gestürzt, oder\).|  
|[get\_DrawWidth](../Topic/CStockPropImpl::get_DrawWidth.md)|Rufen Sie diese Methode auf, um die Zeichnungsbreite abzurufen \(in Pixel\) wird von die Zeichenmethoden des Steuerelements.|  
|[get\_Enabled](../Topic/CStockPropImpl::get_Enabled.md)|Rufen Sie diese Methode auf, um den Status des Flags abzurufen, das angibt, ob das Steuerelement aktiviert wird.|  
|[get\_FillColor](../Topic/CStockPropImpl::get_FillColor.md)|Rufen Sie diese Methode auf, um die Füllfarbe des Steuerelements abzurufen.|  
|[get\_FillStyle](../Topic/CStockPropImpl::get_FillStyle.md)|Rufen Sie diese Methode auf, um den Füllstil des Steuerelements der beispielsweise Vollton\-, transparentes abzurufen oder schraffierte mit sich kreuzenden Linien.|  
|[get\_Font](../Topic/CStockPropImpl::get_Font.md)|Rufen Sie diese Methode auf, um einen Zeiger auf die Schriftarteigenschaften des Steuerelements abzurufen.|  
|[get\_ForeColor](../Topic/CStockPropImpl::get_ForeColor.md)|Rufen Sie diese Methode auf, um die Vordergrundfarbe des Steuerelements abzurufen.|  
|[get\_HWND](../Topic/CStockPropImpl::get_HWND.md)|Rufen Sie diese Methode auf, um das Fensterhandle abzurufen, das dem Steuerelement zugeordnet ist.|  
|[get\_MouseIcon](../Topic/CStockPropImpl::get_MouseIcon.md)|Rufen Sie diese Methode auf, um die Bildeigenschaften der Grafik angezeigt werden \(Symbol, Bitmap oder Metadatei\), wenn die Maus über dem Steuerelement befindet.|  
|[get\_MousePointer](../Topic/CStockPropImpl::get_MousePointer.md)|Rufen Sie diese Methode auf, um den Typ des Mauszeigers abzurufen angezeigt, wenn die Maus über dem Steuerelement, beispielsweise, Pfeil, Kreuz oder Sanduhr ist.|  
|[get\_Picture](../Topic/CStockPropImpl::get_Picture.md)|Rufen Sie diese Methode auf, um einen Zeiger auf die Bildeigenschaften einer Grafik angezeigt werden \(Symbol, Bitmap oder Metadatei\) abzurufen.|  
|[get\_ReadyState](../Topic/CStockPropImpl::get_ReadyState.md)|Rufen Sie diese Methode auf, um den Zustand Bereit des Steuerelements abzurufen beispielsweise laden oder geladen wurde.|  
|[get\_TabStop](../Topic/CStockPropImpl::get_TabStop.md)|Rufen Sie diese Methode auf, um das Flag abzurufen, das angibt, ob das Steuerelement ein Tabstopp oder nicht.|  
|[get\_Text](../Topic/CStockPropImpl::get_Text.md)|Rufen Sie diese Methode auf, um den Text abzurufen, der mit dem Steuerelement angezeigt wird.|  
|[get\_Valid](../Topic/CStockPropImpl::get_Valid.md)|Rufen Sie diese Methode auf, um den Status des Flags abzurufen, das angibt, ob das Steuerelement oder nicht gültig ist.|  
|[get\_Window](../Topic/CStockPropImpl::get_Window.md)|Rufen Sie diese Methode auf, um das Fensterhandle abzurufen, das dem Steuerelement zugeordnet ist.  Identisch mit [CStockPropImpl::get\_HWND](../Topic/CStockPropImpl::get_HWND.md).|  
|[put\_Appearance](../Topic/CStockPropImpl::put_Appearance.md)|Rufen Sie diese Methode auf, um das Farbenformat festzulegen, das vom Steuerelement, beispielsweise, Ebene oder 3D verwendet wird.|  
|[put\_AutoSize](../Topic/CStockPropImpl::put_AutoSize.md)|Rufen Sie diese Methode auf, um den Wert des Flags festzulegen, das angibt, ob das Steuerelement keine andere Größe aufweisen kann.|  
|[put\_BackColor](../Topic/CStockPropImpl::put_BackColor.md)|Rufen Sie diese Methode auf, um die Hintergrundfarbe des Steuerelements festzulegen.|  
|[put\_BackStyle](../Topic/CStockPropImpl::put_BackStyle.md)|Rufen Sie diese Methode auf, um das Hintergrundformat des Steuerelements festzulegen.|  
|[put\_BorderColor](../Topic/CStockPropImpl::put_BorderColor.md)|Rufen Sie diese Methode auf, um die Rahmenfarbe des Steuerelements festzulegen.|  
|[put\_BorderStyle](../Topic/CStockPropImpl::put_BorderStyle.md)|Rufen Sie diese Methode auf, um die Rahmenart des Steuerelements festzulegen.|  
|[put\_BorderVisible](../Topic/CStockPropImpl::put_BorderVisible.md)|Rufen Sie diese Methode auf, um den Wert des Flags festzulegen, das angibt, ob der Ränder des Steuerelements oder ausgeblendet ist.|  
|[put\_BorderWidth](../Topic/CStockPropImpl::put_BorderWidth.md)|Rufen Sie diese Methode auf, um die Breite des Rahmens des Steuerelements festzulegen.|  
|[put\_Caption](../Topic/CStockPropImpl::put_Caption.md)|Rufen Sie diese Methode auf, um den mit dem Steuerelement anzuzeigende Text festzulegen.|  
|[put\_DrawMode](../Topic/CStockPropImpl::put_DrawMode.md)|Rufen Sie diese Methode auf, um den Zeichnungsmodus des Steuerelements, beispielsweise, XOR\-Stift festzulegen oder Farben umzukehren.|  
|[put\_DrawStyle](../Topic/CStockPropImpl::put_DrawStyle.md)|Rufen Sie diese Methode auf, um das Zeichnungsformat des Steuerelements, den beispielsweise, Vollton\- festzulegen, gestürzt, oder\).|  
|[put\_DrawWidth](../Topic/CStockPropImpl::put_DrawWidth.md)|Rufen Sie diese Methode auf, um die Breite festzulegen \(in Pixel\) wird von die Zeichenmethoden des Steuerelements.|  
|[put\_Enabled](../Topic/CStockPropImpl::put_Enabled.md)|Rufen Sie diese Methode auf, um das Flag festlegen, das angibt, wenn das Steuerelement aktiviert ist.|  
|[put\_FillColor](../Topic/CStockPropImpl::put_FillColor.md)|Rufen Sie diese Methode auf, um die Füllfarbe des Steuerelements festzulegen.|  
|[put\_FillStyle](../Topic/CStockPropImpl::put_FillStyle.md)|Rufen Sie diese Methode auf, um den Füllstil des Steuerelements der beispielsweise Vollton\-, transparent festzulegen oder schraffierte mit sich kreuzenden Linien.|  
|[put\_Font](../Topic/CStockPropImpl::put_Font.md)|Rufen Sie diese Methode auf, um die Schriftarteigenschaften des Steuerelements festzulegen.|  
|[put\_ForeColor](../Topic/CStockPropImpl::put_ForeColor.md)|Rufen Sie diese Methode auf, um die Vordergrundfarbe des Steuerelements festzulegen.|  
|[put\_HWND](../Topic/CStockPropImpl::put_HWND.md)|Diese Methode gibt E\_FAIL zurück.|  
|[put\_MouseIcon](../Topic/CStockPropImpl::put_MouseIcon.md)|Rufen Sie diese Methode auf, um die Bildeigenschaften der Grafik angezeigt werden \(Symbol, Bitmap oder Metadatei\) festzulegen, wenn die Maus über dem Steuerelement befindet.|  
|[put\_MousePointer](../Topic/CStockPropImpl::put_MousePointer.md)|Rufen Sie diese Methode auf, um den Typ des Mauszeigers festzulegen angezeigt, wenn die Maus über dem Steuerelement, beispielsweise, Pfeil, Kreuz oder Sanduhr ist.|  
|[put\_Picture](../Topic/CStockPropImpl::put_Picture.md)|Rufen Sie diese Methode auf, um die Bildeigenschaften einer Grafik angezeigt werden \(Symbol, Bitmap oder Metadatei\) festzulegen.|  
|[put\_ReadyState](../Topic/CStockPropImpl::put_ReadyState.md)|Rufen Sie diese Methode auf, um den Zustand Bereit des Steuerelements festzulegen beispielsweise laden oder geladen wurde.|  
|[put\_TabStop](../Topic/CStockPropImpl::put_TabStop.md)|Rufen Sie diese Methode auf, um den Wert des Flags festzulegen, das angibt, ob das Steuerelement ein Tabstopp oder nicht.|  
|[put\_Text](../Topic/CStockPropImpl::put_Text.md)|Rufen Sie diese Methode auf, um den Text festzulegen, der mit dem Steuerelement angezeigt wird.|  
|[put\_Valid](../Topic/CStockPropImpl::put_Valid.md)|Rufen Sie diese Methode auf, um das Flag festlegen, das angibt, wenn das Steuerelement oder nicht gültig ist.|  
|[put\_Window](../Topic/CStockPropImpl::put_Window.md)|Diese Methode ruft [CStockPropImpl::put\_HWND](../Topic/CStockPropImpl::put_HWND.md), das E\_FAIL zurückgibt.|  
|[putref\_Font](../Topic/CStockPropImpl::putref_Font.md)|Rufen Sie diese Methode auf, um die Schriftarteigenschaften des Steuerelements, mit einem Verweiszähler festzulegen.|  
|[putref\_MouseIcon](../Topic/CStockPropImpl::putref_MouseIcon.md)|Rufen Sie diese Methode auf, um die Bildeigenschaften der, wenn die Maus über dem Steuerelement befindet, mit einem Verweiszähler angezeigt werden \(Grafik Symbol, Bitmap oder Metadatei\) festzulegen.|  
|[putref\_Picture](../Topic/CStockPropImpl::putref_Picture.md)|Rufen Sie diese Methode auf, um die Bildeigenschaften einer, mit einem Verweiszähler angezeigt werden \(Grafik Symbol, Bitmap oder Metadatei\) festzulegen.|  
  
## Hinweise  
 `CStockPropImpl` stellt **put** und **get**\-Methoden für jede Eigenschaft vorrätigen Artikel.  Diese Methoden stellen den Code, der, den Datenmember festzulegen oder abzurufen erforderlich ist, der mit jeder Eigenschaft und mit dem Container zu benachrichtigen und Synchronisieren zugeordnet wird, wenn eine Eigenschaft ändert.  
  
 Visual C\+\+ bietet Unterstützung für vordefinierte Eigenschaften durch den Assistenten.  Weitere Informationen zum Hinzufügen von vordefinierten Eigenschaften zu einem Steuerelement, finden Sie unter [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  
  
 Für die Abwärtskompatibilität macht `CStockPropImpl` auch `get_Window` und `put_Window`\-Methoden, die einfach `get_HWND` und `put_HWND` aufrufen, bzw. verfügbar.  Die Standardimplementierung von `put_HWND` gibt **E\_FAIL** zurück, da `HWND` eine schreibgeschützte Eigenschaft sein sollte.  
  
 Die folgenden Eigenschaften haben auch eine **putref** Implementierung:  
  
-   Schriftart  
  
-   MouseIcon  
  
-   Bild  
  
 Die gleichen drei vordefinierten Eigenschaften erfordern ihren entsprechenden Datenmember, vom Typ `CComPtr` oder von einer anderen Klasse, die richtige Schnittstellenverweiszählung mithilfe des Zuweisungsoperators bereitstellt.  
  
## Vererbungshierarchie  
 `T`  
  
 [IDispatchImpl](../../atl/reference/idispatchimpl-class.md)  
  
 `CStockPropImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [IDispatchImpl Class](../../atl/reference/idispatchimpl-class.md)