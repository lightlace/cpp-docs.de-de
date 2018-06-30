---
title: CWinFormsControl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ec945c5f0cdbb0c12f49b90719c31bf841ef2f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121636"
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
 Ein .NET Framework Windows Forms-Steuerelement in der MFC-Anwendung angezeigt werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Erstellt ein Wrapperobjekt für MFC-Windows Forms-Steuerelement.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Erstellt eine Windows Forms-Steuerelement in einem MFC-Container.|  
|[CWinFormsControl::GetControl](#getcontrol)|Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Ruft ein Handle für das Windows Forms-Steuerelement ab.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CWinFormsControl` -Klasse stellt die grundlegende Funktionalität für das Hosten eines Windows Forms-Steuerelements bereit.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 MFC-Code sollten nicht im cache Fensterhandles (gespeichert in der Regel `m_hWnd`). Einige Windows Forms-Steuerelementeigenschaften erfordern, dass die zugrunde liegenden Win32 `Window` zerstört und neu erstellt, mit `DestroyWindow` und `CreateWindow`. Die MFC-Windows Forms-Handles Implementierung der `Destroy` und `Create` Ereignisse der Steuerelemente beim Aktualisieren der `m_hWnd` Member.  
  
> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft (in der AFXDLL definiert ist).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl  
 Erstellt eine Windows Forms-Steuerelement in einem MFC-Container.  
  
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
 *PGeben*  
 Der Datentyp des Steuerelements erstellt werden. Muss ein [Typ](https://msdn.microsoft.com/en-us/library/system.type) -Datentyp.  
  
 *dwStyle*  
 Der Fensterstil, um auf das Steuerelement angewendet werden soll. Geben Sie eine Kombination von [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles). Derzeit werden nur die folgenden Formate unterstützt: WS_TABSTOP, WS_VISIBLE, WS_DISABLED und WS_GROUP.  
  
 *Rect*  
 Ein [RECT-Struktur](../../mfc/reference/rect-structure1.md) , definiert die Koordinaten der oberen linken und unteren rechten Ecke des Steuerelements (zunächst nur Überladung).  
  
 *nPlaceHolderID*  
 Das Handle des Steuerelements Inhaber statische Stelle platziert der Ressourcen-Editor. Das neu erstellte Windows Forms-Steuerelement ersetzt das statische-Steuerelement, vorausgesetzt, die Position, die Z-Reihenfolge und die Stile (nur zweite Überladung).  
  
 *pParentWnd*  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 *nID*  
 Die Ressourcen-ID-Nummer, die neu erstellte Steuerelement zugewiesen werden soll.  
  
 *pControl*  
 Eine Instanz eines Windows Forms-Steuerelements zugeordnet werden die [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) Objekt (vierte Überladung).  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt einen Wert ungleich NULL zurück. Wenn Fehler auftreten, gibt Sie 0 (null) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird .NET Framework Windows Forms-Steuerelements in einem MFC-Container instanziiert.  
  
 Die erste Überladung der Methode akzeptiert einen .NET Framework-Datentyp *PGeben* , damit ein neues Objekt dieses Typs von MFC instanziiert werden kann. *PGeben* muss ein [Typ](https://msdn.microsoft.com/en-us/library/system.type) -Datentyp.  
  
 Die zweite Überladung der Methode erstellt ein Windows Forms-Steuerelement, das basierend auf den `TManagedControl` Vorlagenparameter, der die `CWinFormsControl` Klasse. Die Größe und Position des Steuerelements basiert auf der `RECT` Struktur an die Methode übergeben. Nur *DwStyle* ist relevant für die Stile.  
  
 Die dritte Überladung der Methode erstellt ein Windows Forms-Steuerelement, das ein statisches Steuerelement zerstören und vorausgesetzt, seine Position, die Z-Reihenfolge und die Stile ersetzt. Statische Steuerelement dient nur als Platzhalter für das Windows Forms-Steuerelement. Wenn Sie das Steuerelement zu erstellen, kombiniert diese Überladung der Stile aus *DwStyle* mit der statischen Steuerelement Ressource Formatvorlagen.  
  
 Die vierte Überladung der Methode können Sie eine bereits instanziierte Windows Forms-Steuerelement übergeben *pControl* , die MFC umbrochen wird. Muss er den gleichen Typ aufweisen wie die `TManagedControl` Vorlagenparameter, der die `CWinFormsControl` Klasse.  
  
 Finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) Beispiele zur Verwendung von Windows Forms steuert.  
  
##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl  
 Erstellt ein Wrapperobjekt für MFC-Windows Forms-Steuerelement.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Hinweise  
 Windows Forms-Steuerelement wird instanziiert, wenn Sie rufen [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrol"></a>  CWinFormsControl::GetControl  
 Ruft einen Zeiger auf das Windows Forms-Steuerelement ab.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf das Windows Forms-Steuerelement zurück.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle  
 Ruft ein Handle für das Windows Forms-Steuerelement ab.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Handle auf das Windows Forms-Steuerelement zurück.  
  
### <a name="remarks"></a>Hinweise  
 `GetControlHandle` ist eine Hilfsmethode, die das Fensterhandle gespeichert, in der .NET Framework-Steuerelementeigenschaften zurückgibt. Der Wert für Dienstfenster Handle in kopiert [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) während des Aufrufs [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;  
 Ersetzt [CWinFormsControl::GetControl](#getcontrol) in Ausdrücken.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bietet eine einfache Syntax, die ersetzt `GetControl` in Ausdrücken.  
  
 Weitere Informationen zu Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^  
 Wandelt einen Typ ein Zeiger auf ein Windows Forms-Steuerelement.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator übergibt `CWinFormsControl<TManagedControl>` auf Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement zu akzeptieren.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinFormsDialog-Klasse](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)
