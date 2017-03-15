---
title: CSpinButtonCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [C++], CSpinButtonCtrl
- CSpinButtonCtrl class
- CSpinButtonCtrl class, common controls
- up-down controls, spin button control
- spin button control
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
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
ms.openlocfilehash: 486a0842ed04f0e760bbb332986a97a35ce9851f
ms.lasthandoff: 02/24/2017

---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Drehfeld-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Erstellt ein `CSpinButtonCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Erstellt ein Drehfeld-Steuerelement und fügt es ein `CSpinButtonCtrl` Objekt.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Erstellt ein Drehfeld-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CSpinButtonCtrl` Objekt.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Ruft die Beschleunigung Informationen für ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::GetBase](#getbase)|Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Ruft einen Zeiger auf das aktuelle Buddyfenster.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Ruft die aktuelle Position des Drehfeld-Steuerelements ab.|  
|[CSpinButtonCtrl::GetRange](#getrange)|Ruft die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement ab.|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Legt die Beschleunigung für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetBase](#setbase)|Legt die Basis für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Legt das Buddyfenster für ein Drehfeld-Steuerelement fest.|  
|[CSpinButtonCtrl::SetPos](#setpos)|Legt die aktuelle Position für das Steuerelement fest.|  
|[CSpinButtonCtrl:: SetRange](#setrange)|Legt die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 "Drehfeld-Steuerelements" (auch als auf-ab-Steuerelement bezeichnet) ist ein Paar von Pfeilschaltflächen, die der Benutzer klicken kann, um inkrementiert oder dekrementiert einen Wert ein, z. B. eine Bildlaufposition oder eine Zahl, die in einem separaten Steuerelement angezeigt. Ein Drehfeld-Steuerelement zugeordnete Wert wird die aktuelle Position aufgerufen. Ein Drehfeld-Steuerelement wird am häufigsten mit einem Begleit-Steuerelement aufgerufen, als "Buddy-Fenster" verwendet.  
  
 Dieses Steuerelement (und somit die `CSpinButtonCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Sehen für den Benutzer ein Drehfeldsteuerelement oft das Buddyfenster wie ein einzelnes Steuerelement ein. Sie können angeben, dass ein Drehfeld-Steuerelement selbst automatisch neben der Buddyfenster, positionieren und sie automatisch die Beschriftung des Buddy-Fensters auf der aktuellen Position festgelegt. Ein Drehfeld-Steuerelement können mit einem Bearbeitungssteuerelement die Benutzer für numerische Eingabe aufzufordern.  
  
 Auf den Pfeil nach oben verschiebt die aktuelle Position für die maximale Anzahl, und klicken auf den Pfeil nach unten Verschiebt die aktuelle Position in Richtung Minimum. Standardmäßig beträgt 100 und der maximale Wert ist 0. Jedes Mal, wenn der niedrigste Wert ist größer als die maximale Einstellung (z. B. wenn die Standardeinstellungen verwendet werden), klicken oben Pfeil reduziert erhöht den Positionswert und auf den Pfeil nach unten.  
  
 Ein Drehfeld-Steuerelement ohne als Buddy-Fenster fungiert als eine Art vereinfachte Bildlaufleiste. Beispielsweise zeigt ein Registerkarten-Steuerelement manchmal ein Drehfeldsteuerelement, um dem Benutzer ermöglichen, zusätzliche Registerkarten Bildlauf.  
  
 Weitere Informationen zur Verwendung von `CSpinButtonCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-namecreatea--cspinbuttonctrlcreate"></a><a name="create"></a>CSpinButtonCtrl::Create  
 Erstellt ein Drehfeld-Steuerelement und fügt es ein `CSpinButtonCtrl` Objekt...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Drehfeldsteuerelement-Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile Steuerelement auf das Steuerelement anzuwenden. Diese Stile werden im Abschnitt [auf-ab-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb759885) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt des Drehfeld-Steuerelements die Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur  
  
 `pParentWnd`  
 Ein Zeiger auf das Drehfeld-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Er darf nicht sein **NULL.**  
  
 `nID`  
 Gibt das Drehfeld-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CSpinButtonCtrl` Objekt in zwei Schritten zuerst, rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, der das Drehfeld-Steuerelement erstellt, und fügt es der `CSpinButtonCtrl` Objekt.  
  
 Rufen Sie zum Erstellen einer Drehfeld-Steuerelement mit erweiterten Fensterstile [CSpinButtonCtrl::CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="a-namecreateexa--cspinbuttonctrlcreateex"></a><a name="createex"></a>CSpinButtonCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CSpinButtonCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Gibt das Drehfeldsteuerelement-Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile Steuerelement auf das Steuerelement anzuwenden. Diese Stile werden im Abschnitt [auf-ab-Steuerelementstile](http://msdn.microsoft.com/library/windows/desktop/bb759885) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="a-namecspinbuttonctrla--cspinbuttonctrlcspinbuttonctrl"></a><a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 Erstellt ein `CSpinButtonCtrl`-Objekt.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="a-namegetaccela--cspinbuttonctrlgetaccel"></a><a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 Ruft die Beschleunigung Informationen für ein Drehfeld-Steuerelement ab.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nAccel`  
 Anzahl der Elemente im angegebenen Array `pAccel`.  
  
 `pAccel`  
 Zeiger auf ein Array von [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) -Strukturen, die Beschleunigung Informationen erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Zugriffstaste Strukturen abgerufen.  
  
##  <a name="a-namegetbasea--cspinbuttonctrlgetbase"></a><a name="getbase"></a>CSpinButtonCtrl::GetBase  
 Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Basiswert.  
  
##  <a name="a-namegetbuddya--cspinbuttonctrlgetbuddy"></a><a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 Ruft einen Zeiger auf das aktuelle Buddyfenster.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das aktuelle Buddyfenster.  
  
##  <a name="a-namegetposa--cspinbuttonctrlgetpos"></a><a name="getpos"></a>CSpinButtonCtrl::GetPos  
 Ruft die aktuelle Position des Drehfeld-Steuerelements ab.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  ```  
  
### Parameters  
 *lpbError*  
 A pointer to a boolean value that is set to zero if the value is successfully retrieved or non-zero if an error occurs. If this parameter is set to **NULL**, errors are not reported.  
  
### Return Value  
 The first version returns the 16-bit current position in the low-order word. The high-order word is nonzero if an error occurred.  
  
 The second version returns the 32-bit position.  
  
### Remarks  
 When it processes the value returned, the control updates its current position based on the caption of the buddy window. The control returns an error if there is no buddy window or if the caption specifies an invalid or out-of-range value.  
  
##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange  
 Retrieves the upper and lower limits (range) for a spin button control.  
  
```  
DWORD GetRange() const;  
  
void GetRange (Int & verringern  
    Int & oben) const;  
  
void GetRange32 (Int & niedriger  
    Int & oben) const;  
```  
  
### Parameters  
 *lower*  
 Reference to an integer that receives the lower limit for the control.  
  
 *upper*  
 Reference to an integer that receives the upper limit for the control.  
  
### Return Value  
 The first version returns a 32-bit value containing the upper and lower limits. The low-order word is the upper limit for the control, and the high-order word is the lower limit.  
  
### Remarks  
 The member function `GetRange32` retrieves the spin button control's range as a 32-bit integer.  
  
##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel  
 Sets the acceleration for a spin button control.  
  
```  
BOOL Memberfunktionen SetAccel (Int nAccel,  
    UDACCEL* pAccel);
```  
  
### Parameters  
 `nAccel`  
 Number of [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) structures specified by `pAccel`.  
  
 `pAccel`  
 Pointer to an array of `UDACCEL` structures, which contain acceleration information. Elements should be sorted in ascending order based on the **nSec** member.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase  
 Sets the base for a spin button control.  
  
```  
Int SetBase (Int nBase);
```  
  
### Parameters  
 `nBase`  
 New base value for the control. It can be 10 for decimal or 16 for hexadecimal.  
  
### Return Value  
 The previous base value if successful, or zero if an invalid base is given.  
  
### Remarks  
 The base value determines whether the buddy window displays numbers in decimal or hexadecimal digits. Hexadecimal numbers are always unsigned; decimal numbers are signed.  
  
##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy  
 Sets the buddy window for a spin button control.  
  
```  
CWnd* SetBuddy (CWnd* pWndBuddy);
```  
  
### Parameters  
 `pWndBuddy`  
 Pointer to the new buddy window.  
  
### Return Value  
 A pointer to the previous buddy window.  
  
### Remarks  
 A spin control is almost always associated with another window, such as an edit control, that displays some content. This other window is called the "buddy" of the spin control.  
  
##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos  
 Sets the current position for a spin button control.  
  
```  
Int-Memberfunktion SetPos (Int nPos);  
Int SetPos32(int nPos).
```  
  
### Parameters  
 `nPos`  
 New position for the control. This value must be in the range specified by the upper and lower limits for the control.  
  
### Return Value  
 The previous position (16-bit precision for `SetPos`, 32-bit precision for `SetPos32`).  
  
### Remarks  
 `SetPos32` sets the 32-bit position.  
  
##  <a name="setrange"></a>  CSpinButtonCtrl::SetRange  
 Sets the upper and lower limits (range) for a spin button control.  
  
```  
void SetRange (kurze nLower,  
    kurze nUpper);

 
void SetRange32 (Int nLower,  
    Int nUpper);
```  
  
### Parameters  
 `nLower`and `nUpper`  
 Upper and lower limits for the control. For `SetRange`, neither limit can be greater than **UD_MAXVAL** or less than **UD_MINVAL**; in addition, the difference between the two limits cannot exceed **UD_MAXVAL**. `SetRange32` places no restrictions on the limits; use any integers.  
  
### Remarks  
 The member function `SetRange32` sets the 32-bit range for the spin button control.  
  
> [!NOTE]
>  The default range for the spin button has the maximum set to zero (0) and the minimum set to 100. Because the maximum value is less than the minimum value, clicking the up arrow will decrease the position and clicking the down arrow will increase it. Use `CSpinButtonCtrl::SetRange` to adjust these values.  
  
## See Also  
 [MFC Sample CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd Class](../../mfc/reference/cwnd-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Class](../../mfc/reference/csliderctrl-class.md)

