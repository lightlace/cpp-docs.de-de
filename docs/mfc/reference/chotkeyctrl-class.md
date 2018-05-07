---
title: CHotKeyCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 590914ac312a4f998eb759beb08ed2e7935874fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Abkürzungstasten-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Erstellt ein `CHotKeyCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Erstellt eine Abkürzungstasten-Steuerelements, und fügt es einer `CHotKeyCtrl` Objekt.|  
|[CHotKeyCtrl::CreateEx](#createex)|Erstellt eine Abkürzungstasten-Steuerelements mit der angegebenen erweiterten Fensterstile und fügt es einer `CHotKeyCtrl` Objekt.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Ruft die virtuellen Key Code und der Modifizierer Flags einer Abkürzungstaste aus eines Abkürzungstasten-Steuerelements ab.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Ruft den Schlüsselnamen in den lokalen Zeichensatz einer Abkürzungstaste zugewiesen.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Ruft den Schlüsselnamen in den lokalen Zeichensatz, den angegebenen virtueller Tastencode zugewiesen.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Legt die Tastenkombination für einen Abkürzungstasten-Steuerelements fest.|  
|[CHotKeyCtrl::SetRules](#setrules)|Definiert die ungültigen Kombinationen und die Standard-Modifizierer Kombination für eines Abkürzungstasten-Steuerelements.|  
  
## <a name="remarks"></a>Hinweise  
 Eine "Abkürzungstaste-Steuerelement" ist ein Fenster, das dem Benutzer ermöglicht, eine Abkürzungstaste erstellen. Eine "Abkürzungstaste" ist eine Tastenkombination, die der Benutzer drücken kann, um eine Aktion schnell ausgeführt. (Z. B. kann ein Benutzer eine Abkürzungstaste, die ein bestimmtes Fenster aktiviert und schaltet sie am Anfang der Z-Reihenfolge erstellen.) Die Abkürzungstasten-Steuerelements zeigt die Auswahl des Benutzers an und stellt sicher, dass der Benutzer eine gültige Tastenkombination auswählt.  
  
 Dieses Steuerelement (und somit die `CHotKeyCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird.  
  
 Wenn der Benutzer eine Tastenkombination ausgewählt hat, die Anwendung die angegebene Tastenkombination aus dem Steuerelement abrufen und Verwenden der **WM_SETHOTKEY** Nachricht im System die Abkürzungstaste einrichten. Wenn der Benutzer die Zugriffstaste aus einem beliebigen Teil des Systems danach drückt des Fensters angegeben, der **WM_SETHOTKEY** Nachricht empfängt eine `WM_SYSCOMMAND` Nachricht angeben **SC_HOTKEY**. Diese Meldung aktiviert das Fenster, das es empfängt. Die Abkürzungstaste bleibt gültig, bis die Anwendung, die aufgerufen **WM_SETHOTKEY** beendet wird.  
  
 Dieser Mechanismus unterscheidet sich von der hot Key Unterstützung, von denen abhängt der **WM_HOTKEY** Nachricht und die Windows- [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) und [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) Funktionen.  
  
 Weitere Informationen zur Verwendung von `CHotKeyCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl  
 Erstellt ein `CHotKeyCtrl`-Objekt.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>  CHotKeyCtrl::Create  
 Erstellt eine Abkürzungstasten-Steuerelements, und fügt es einer `CHotKeyCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt die Abkürzungstasten-Steuerelements Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) in das Windows SDK für Weitere Informationen.  
  
 `rect`  
 Gibt an, die Abkürzungstasten-Steuerelements die Größe und Position. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT-Struktur](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Gibt an, die Abkürzungstasten-Steuerelements des übergeordneten Fensters, in der Regel eine [CDialog](../../mfc/reference/cdialog-class.md). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt die Abkürzungstasten-Steuerelements ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CHotKeyCtrl` Objekt in zwei Schritten. Zuerst wird den Konstruktor aufrufen und dann **erstellen**, das erstellt die Abkürzungstasten-Steuerelements, und fügt es der `CHotKeyCtrl` Objekt.  
  
 Wenn Sie die erweiterten Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>  CHotKeyCtrl::CreateEx  
 Mit dieser Funktion wird zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CHotKeyCtrl` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Gibt die Abkürzungstasten-Steuerelements Stil. Wenden Sie eine beliebige Kombination von Steuerelementtypen. Weitere Informationen finden Sie unter [Steuerelementtypen für die allgemeine](http://msdn.microsoft.com/library/windows/desktop/bb775498) im Windows SDK.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey  
 Ruft den virtuellen Key Code und der Modifizierer Flags auf, der eine Tastenkombination aus eines Abkürzungstasten-Steuerelements ab.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `wVirtualKeyCode`  
 Virtueller Tastencode der Tastenkombination zugreifen. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie unter Winuser.h.  
  
 [out] `wModifiers`  
 Eine bitweise Kombination (OR) von Flags, die in die Tastenkombination Zusatztasten angeben.  
  
 Die Modifiziererflags sind wie folgt aus:  
  
|Flag|Entsprechenden Schlüssel|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT-TASTE|  
|`HOTKEYF_CONTROL`|STRG-Taste|  
|`HOTKEYF_EXT`|Erweiterte Schlüssel|  
|`HOTKEYF_SHIFT`|Umschalttaste gedrückt|  
  
### <a name="return-value"></a>Rückgabewert  
 Im ersten überladene Methode, eine `DWORD` virtuellen Key Code und der Modifizierer Flags enthält. Das niedrige Byte das niederwertige Wort enthält den virtuellen Tastencode, das höherwertige Byte das niederwertige Wort enthält die Modifiziererflags und das höherwertige Wort ist 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Definieren die Tastenkombination den virtueller Tastencode und der Zusatztasten zusammen.  
  
##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName  
 Rufen Sie diese Memberfunktion um den lokalisierten Namen des Schlüssels im laufenden Systembetrieb zu erhalten.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der lokalisierte Name des aktuell ausgewählten Abkürzungstaste. Es ist keine ausgewählten Abkürzungstaste `GetHotKeyName` eine leere Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Name, der diese Memberfunktion gibt stammt aus dem Tastaturtreiber. Sie können einen Tastaturtreiber nicht lokalisierten in einer lokalisierten Version von Windows installieren und umgekehrt.  
  
##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName  
 Rufen Sie diese Memberfunktion zum Abrufen der lokalisierte Name des Schlüssels, der einen angegebenen virtuellem Tastencode zugewiesen.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Parameter  
 `vk`  
 Den virtueller Tastencode.  
  
 *fExtended*  
 Der virtuelle Tastencode ist eine erweiterte Schlüssel **"true"** andernfalls **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Der lokalisierte Name des Schlüssels angegeben wird, indem Sie die `vk` Parameter. Wenn der Schlüssel keinen zugeordneten Namen besitzt, `GetKeyName` eine leere Zeichenfolge zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Der Name, der diese Funktion gibt stammt aus dem Tastaturtreiber einen Tastaturtreiber nicht lokalisierten in einer lokalisierten Version von Windows installiert werden können und umgekehrt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey  
 Legt die Tastenkombination für einen Abkürzungstasten-Steuerelements fest.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wVirtualKeyCode`  
 Virtueller Tastencode der Tastenkombination zugreifen. Eine Liste der standardmäßigen virtuellen Tastencodes finden Sie unter Winuser.h.  
  
 [in] `wModifiers`  
 Eine bitweise Kombination (OR) von Flags, die in die Tastenkombination Zusatztasten angeben.  
  
 Die Modifiziererflags sind wie folgt aus:  
  
|Flag|Entsprechenden Schlüssel|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT-TASTE|  
|`HOTKEYF_CONTROL`|STRG-Taste|  
|`HOTKEYF_EXT`|Erweiterte Schlüssel|  
|`HOTKEYF_SHIFT`|Umschalttaste gedrückt|  
  
### <a name="remarks"></a>Hinweise  
 Definieren die Tastenkombination den virtueller Tastencode und der Zusatztasten zusammen.  
  
##  <a name="setrules"></a>  CHotKeyCtrl::SetRules  
 Mit dieser Funktion wird zum Definieren der ungültigen Optionskombinationen und die Standard-Modifizierer Kombination für eines Abkürzungstasten-Steuerelements.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Parameter  
 `wInvalidComb`  
 Ein Array von Flags, die ungültige Schlüsselkombinationen angibt. Eine Kombination der folgenden Werte sind möglich:  
  
- `HKCOMB_A` ALT-TASTE  
  
- `HKCOMB_C` STRG  
  
- `HKCOMB_CA` STRG + ALT  
  
- `HKCOMB_NONE` Unveränderte Schlüssel  
  
- `HKCOMB_S` UMSCHALTTASTE GEDRÜCKT  
  
- `HKCOMB_SA` UMSCHALT + ALT  
  
- `HKCOMB_SC` UMSCHALT + STRG  
  
- `HKCOMB_SCA` UMSCHALT + STRG + ALT  
  
 `wModifiers`  
 Ein Array von Flags, die angibt, die Tastenkombination zu verwenden, wenn der Benutzer eine ungültige Kombination gibt. Weitere Informationen zu den Modifiziererflags finden Sie unter [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Benutzer eine ungültige Tastenkombination eingibt, gemäß der Definition von Flags, die im angegebenen `wInvalidComb`, verwendet das System den OR-Operator, um die mit den Flags, die im angegebenen vom Benutzer eingegebenen Schlüssel zu kombinieren `wModifiers`. Die resultierende Tastenkombination wird in eine Zeichenfolge konvertiert und dann in die Abkürzungstasten-Steuerelements angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



