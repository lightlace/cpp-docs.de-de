---
title: CWinFormsControl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsControl
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsControl class
- Windows Forms [C++], MFC support
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
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
ms.openlocfilehash: 49e24c04deda3df5683908fa9ca485cf7802214b
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformscontrol-class"></a>CWinFormsControl-Klasse
Stellt die grundlegende Funktionalität zum Hosten eines Windows Forms-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Parameter  
 `TManagedControl`  
 Ein .NET Framework Windows Forms-Steuerelement in der MFC-Anwendung angezeigt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Erstellt ein MFC-Windows Forms-Steuerelement-Wrapper-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Erstellt eine Windows Forms-Steuerelements in einem MFC-Container.|  
|[CWinFormsControl::GetControl](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Ruft ein Handle für das Windows Forms-Steuerelement ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CWinFormsControl` -Klasse stellt die grundlegende Funktionalität für das Hosten eines Windows Forms-Steuerelements bereit.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 MFC-Code sollten nicht zwischenspeichern, Fensterhandles (gespeichert in der Regel `m_hWnd`). Einige Windows Forms-Steuerelement-Eigenschaften benötigen, die die zugrunde liegende Win32 `Window` zerstört und neu erstellt, mit `DestroyWindow` und `CreateWindow`. Die MFC-Windows Forms-Implementierung behandelt die `Destroy` und `Create` Ereignisse der Steuerelemente zum Aktualisieren der `m_hWnd` Member.  
  
> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft (in denen AFXDLL definiert ist).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="a-namecreatemanagedcontrola--cwinformscontrolcreatemanagedcontrol"></a><a name="createmanagedcontrol"></a>CWinFormsControl::CreateManagedControl  
 Erstellt eine Windows Forms-Steuerelements in einem MFC-Container.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Parameter  
 `pType`  
 Der Datentyp des Steuerelements erstellt werden. Muss ein [Typ](https://msdn.microsoft.com/en-us/library/system.type) -Datentyp.  
  
 `dwStyle`  
 Der Fensterstil auf das Steuerelement angewendet werden soll. Geben Sie eine Kombination von [Fensterstile](../../mfc/reference/window-styles.md). Derzeit werden nur die folgenden Formate unterstützt: WS_TABSTOP, WS_VISIBLE, WS_DISABLED und WS_GROUP.  
  
 `rect`  
 Ein [RECT-Struktur](../../mfc/reference/rect-structure1.md) , definiert die Koordinaten der oberen linken und der unteren rechten Ecke des Steuerelements (nur erste Überladung).  
  
 `nPlaceHolderID`  
 Das Handle des Steuerelements Inhaber statische Stelle platziert im Ressourcen-Editor. Das neu erstellte Windows Forms-Steuerelement ersetzt das statische-Steuerelement, vorausgesetzt, seine Position, den Z-Reihenfolge und die Stile (nur zweite Überladung).  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 `nID`  
 Die Ressourcen-ID-Nummer, die neu erstellte Steuerelement zugewiesen werden soll.  
  
 `pControl`  
 Eine Instanz eines Windows Forms-Steuerelements zugeordnet werden die [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) Objekt (vierte Überladung).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall wird einen Wert ungleich NULL zurückgegeben. Wenn dies nicht gelingt, gibt NULL zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine .NET Framework Windows Forms-Steuerelement in ein MFC-Container.  
  
 Die erste Überladung der Methode akzeptiert einen .NET Framework-Datentyp `pType` so, dass MFC ein neues Objekt dieses Typs instanziiert werden kann. `pType`muss ein [Typ](https://msdn.microsoft.com/en-us/library/system.type) -Datentyp.  
  
 Die zweite Überladung der Methode erstellt ein Windows Forms-Steuerelement auf der Grundlage der `TManagedControl` Vorlagenparameter, der die `CWinFormsControl` Klasse. Die Größe und Position des Steuerelements basiert auf der `RECT` Struktur an die Methode übergeben. Nur `dwStyle` ist wichtig für die Formate.  
  
 Die dritte Überladung der Methode erstellt ein Windows Forms-Steuerelement, das ein statisches Steuerelement zu zerstören und vorausgesetzt, seine Position, den Z-Reihenfolge und die Stile ersetzt. Statische Steuerelement fungiert nur als Platzhalter für Windows Forms-Steuerelement. Wenn Sie das Steuerelement zu erstellen, kombiniert diese Überladung die Formatvorlagen in `dwStyle` mit der statischen Steuerelements Ressource Formatvorlagen.  
  
 Die vierte Überladung der Methode können Sie eine bereits instanziierte Windows Forms-Steuerelement übergeben `pControl` , die MFC umbrochen wird. Es muss vom gleichen Typ wie die `TManagedControl` Vorlagenparameter, der die `CWinFormsControl` Klasse.  
  
 Finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Beispiele zur Verwendung von Windows Forms steuert.  
  
##  <a name="a-namecwinformscontrola--cwinformscontrolcwinformscontrol"></a><a name="cwinformscontrol"></a>CWinFormsControl::CWinFormsControl  
 Erstellt ein MFC-Windows Forms-Steuerelement-Wrapper-Objekt.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Windows Forms-Steuerelement instanziiert wird, beim Aufruf von [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="a-namegetcontrola--cwinformscontrolgetcontrol"></a><a name="getcontrol"></a>CWinFormsControl::GetControl  
 Ruft einen Zeiger auf das Windows Forms-Steuerelement.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das Windows Forms-Steuerelement.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="a-namegetcontrolhandlea--cwinformscontrolgetcontrolhandle"></a><a name="getcontrolhandle"></a>CWinFormsControl::GetControlHandle  
 Ruft ein Handle für das Windows Forms-Steuerelement ab.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das Windows Forms-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 `GetControlHandle`ist eine Hilfsmethode, die das Handle des Fensters in den .NET Framework-Steuerelement-Eigenschaften gespeichert zurückgibt. Kopiert der Fensterhandlewert zu [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) während des Aufrufs von [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="a-nameoperator-gta--cwinformscontroloperator--gt"></a><a name="operator_-_gt"></a>CWinFormsControl::operator-&gt;  
 Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bietet eine bequeme Syntax, die ersetzt `GetControl` in Ausdrücken.  
  
 Weitere Informationen zu Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="a-nameoperatortmanagedcontrola--cwinformscontroloperator-tmanagedcontrol"></a><a name="operator_tmanagedcontrol"></a>CWinFormsControl::operator TManagedControl ^  
 Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator übergibt `CWinFormsControl<``TManagedControl``>` Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement zu akzeptieren.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)

