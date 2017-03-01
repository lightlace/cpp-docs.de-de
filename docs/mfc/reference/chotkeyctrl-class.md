---
title: CHotKeyCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
dev_langs:
- C++
helpviewer_keywords:
- hot key controls
- CHotKeyCtrl class
- Windows common controls [C++], CHotKeyCtrl
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
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
ms.openlocfilehash: cbcc720d2b934cde9f8beb9bb95499d9cc569413
ms.lasthandoff: 02/24/2017

---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Abkürzungstasten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Erstellt ein `CHotKeyCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Erstellt ein und fügt es ein `CHotKeyCtrl` Objekt.|  
|[CHotKeyCtrl::CreateEx](#createex)|Erstellt eine Abkürzungstasten-Steuerelements mit dem angegebenen erweiterten Fensterstile und fügt es ein `CHotKeyCtrl` Objekt.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Ruft die virtuellen Schlüssel und Modifiziererflags Flags Zugriffstaste aus eines Abkürzungstasten-Steuerelements ab.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Ruft den Schlüsselnamen in den lokalen Zeichensatz Zugriffstaste zugewiesen.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Ruft den Schlüsselnamen im lokalen Zeichensatz, den angegebenen virtuellen Tastencode zugewiesen.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Legt die Tastenkombination für einen Abkürzungstasten-Steuerelements fest.|  
|[CHotKeyCtrl::SetRules](#setrules)|Definiert die ungültige Kombinationen und die Modifizierer Standardkombination für eines Abkürzungstasten-Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Eine "Abkürzungstaste-Steuerelement" ist ein Fenster, das dem Benutzer ermöglicht, eine Abkürzungstaste erstellen. Eine "Abkürzungstaste" ist eine Tastenkombination, die der Benutzer drücken kann, um eine Aktion schnell ausgeführt. (Z. B. kann ein Benutzer eine Abkürzungstaste, die ein bestimmtes Fenster aktiviert und schaltet sie am Anfang der Z-Reihenfolge erstellen.) Die Abkürzungstasten-Steuerelements wird die Auswahl des Benutzers angezeigt und sichergestellt, dass der Benutzer eine gültige Tastenkombination gewählt.  
  
 Dieses Steuerelement (und somit die `CHotKeyCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.  
  
 Wenn der Benutzer eine Tastenkombination ausgewählt hat, die Anwendung die angegebene Tastenkombination aus dem Steuerelement abrufen und verwenden die **WM_SETHOTKEY** Nachricht in das System die Abkürzungstaste einrichten. Wenn der Benutzer die Zugriffstaste danach von einem beliebigen Teil des Systems drückt Fenster angegeben, der **WM_SETHOTKEY** Nachricht erhält einen `WM_SYSCOMMAND` Nachricht angeben **SC_HOTKEY**. Diese Meldung wird das Fenster, das er erhält aktiviert. Die Abkürzungstaste bleibt gültig, bis die Anwendung, aufgerufen **WM_SETHOTKEY** beendet wird.  
  
 Dieser Mechanismus unterscheidet sich von der aktiven wichtige Unterstützung, die abhängig der **WM_HOTKEY** Nachricht und die Windows- [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) und [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) Funktionen.  
  
 Weitere Informationen zur Verwendung von `CHotKeyCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="a-namechotkeyctrla--chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl  
 Erstellt ein `CHotKeyCtrl`-Objekt.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="a-namecreatea--chotkeyctrlcreate"></a><a name="create"></a>CHotKeyCtrl::Create  
 Erstellt ein und fügt es ein `CHotKeyCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Abkürzungstasten-Steuerelements Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
 `rect`  
 Gibt des Abkürzungstasten-Steuerelements die Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT-Struktur](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Gibt an, die Zugriffstaste des übergeordneten Fensters, in der Regel eine [CDialog](../../mfc/reference/cdialog-class.md). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Abkürzungstaste-Steuerelement ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CHotKeyCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie dann **erstellen**, die die Abkürzungstasten-Steuerelements erstellt und fügt es der `CHotKeyCtrl` Objekt.  
  
 Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="a-namecreateexa--chotkeyctrlcreateex"></a><a name="createex"></a>CHotKeyCtrl::CreateEx  
 Rufen Sie diese Funktion zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CHotKeyCtrl` Objekt.  
  
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
 Gibt die Abkürzungstasten-Steuerelements Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Weitere Informationen finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
  
##  <a name="a-namegethotkeya--chotkeyctrlgethotkey"></a><a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 Ruft die virtuellen Schlüssel und Modifiziererflags Flags eine Tastenkombination aus eines Abkürzungstasten-Steuerelements ab.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `wVirtualKeyCode`  
 Virtueller Tastencode der Tastenkombination. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h.  
  
 [out] `wModifiers`  
 Eine bitweise Kombination (OR) von Flags, die Modifizierertasten in die Tastenkombination angeben.  
  
 Die Modifiziererflags lauten wie folgt:  
  
|Flag|Entsprechenden Schlüssel|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT-TASTE|  
|`HOTKEYF_CONTROL`|STRG-Taste|  
|`HOTKEYF_EXT`|Erweiterte Schlüssel|  
|`HOTKEYF_SHIFT`|Umschalttaste gedrückt|  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten überladene Methode, eine `DWORD` , die die virtuellen Schlüssel und Modifiziererflags Flags enthält. Das untere Byte das niederwertige Wort enthält den virtuellen Tastencode, das höherwertige Byte das niederwertige Wort enthält die Modifiziererflags und das höherwertige Wort ist&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Definieren die Tastenkombination virtueller Tastencode und der Zusatztasten zusammen.  
  
##  <a name="a-namegethotkeynamea--chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 Rufen Sie diese Memberfunktion um den lokalisierten Namen des Tastenkombination zu erhalten.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der lokalisierte Name des aktuell ausgewählten Tastenkombination. Es ist keine ausgewählten Abkürzungstaste `GetHotKeyName` eine leere Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Name, der diese Memberfunktion gibt stammt aus der Tastaturtreiber. Sie können einen Tastaturtreiber nicht lokalisierten in einer lokalisierten Version von Windows installieren und umgekehrt.  
  
##  <a name="a-namegetkeynamea--chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>CHotKeyCtrl::GetKeyName  
 Rufen Sie diese Memberfunktion zum Abrufen der lokalisierte Name des Schlüssels auf einem angegebenen virtuellen Tastencode zugewiesen.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Parameter  
 `vk`  
 Virtueller Tastencode.  
  
 *fExtended*  
 Virtuelle Tastencode ist eine erweiterte Zugriffstaste **TRUE**andernfalls **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Der lokalisierte Name des angegebenen Schlüssels der `vk` Parameter. Wenn der Schlüssel kein zugeordneten Name, hat `GetKeyName` eine leere Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Name des Schlüssels, der diese Funktion gibt stammen aus den Tastaturtreiber, damit einen Tastaturtreiber nicht lokalisierten in einer lokalisierten Version von Windows installiert werden kann und umgekehrt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#69;](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="a-namesethotkeya--chotkeyctrlsethotkey"></a><a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 Legt die Tastenkombination für einen Abkürzungstasten-Steuerelements fest.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wVirtualKeyCode`  
 Virtueller Tastencode der Tastenkombination. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie in Winuser.h.  
  
 [in] `wModifiers`  
 Eine bitweise Kombination (OR) von Flags, die Modifizierertasten in die Tastenkombination angeben.  
  
 Die Modifiziererflags lauten wie folgt:  
  
|Flag|Entsprechenden Schlüssel|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT-TASTE|  
|`HOTKEYF_CONTROL`|STRG-Taste|  
|`HOTKEYF_EXT`|Erweiterte Schlüssel|  
|`HOTKEYF_SHIFT`|Umschalttaste gedrückt|  
  
### <a name="remarks"></a>Hinweise  
 Definieren die Tastenkombination virtueller Tastencode und der Zusatztasten zusammen.  
  
##  <a name="a-namesetrulesa--chotkeyctrlsetrules"></a><a name="setrules"></a>CHotKeyCtrl::SetRules  
 Rufen Sie diese Funktion, um die ungültigen Kombinationen und die Modifizierer Standardkombination für eine Zugriffstaste zu definieren.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parameter  
 `wInvalidComb`  
 Array von Flags, ungültige Tastenkombinationen angibt. Es kann eine Kombination der folgenden Werte sein:  
  
- `HKCOMB_A`ALT-TASTE  
  
- `HKCOMB_C`STRG  
  
- `HKCOMB_CA`STRG + ALT  
  
- `HKCOMB_NONE`Unveränderte Schlüssel  
  
- `HKCOMB_S`UMSCHALTTASTE GEDRÜCKT  
  
- `HKCOMB_SA`UMSCHALT + ALT  
  
- `HKCOMB_SC`UMSCHALT + STRG  
  
- `HKCOMB_SCA`UMSCHALT + STRG + ALT  
  
 `wModifiers`  
 Ein Array von Flags, die angibt, die Tastenkombination zu verwenden, wenn der Benutzer eine ungültige Kombination eingibt. Weitere Informationen über die Modifiziererflags, finden Sie unter [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Benutzer eine ungültige Tastenkombination eingibt, gemäß der in angegebenen Flags `wInvalidComb`, das System verwendet den OR-Operator kombiniert mit dem in angegebenen Flags vom Benutzer eingegebenen Schlüssel `wModifiers`. Die resultierende Tastenkombination in eine Zeichenfolge konvertiert und dann in die Abkürzungstasten-Steuerelements angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




