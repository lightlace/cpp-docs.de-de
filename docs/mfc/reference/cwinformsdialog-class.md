---
title: CWinFormsDialog Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- CWinFormsDialog class
- Windows Forms [C++], MFC support
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
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
ms.openlocfilehash: 86768a849b0112f7c4f8b6b2a694b80065169575
ms.lasthandoff: 02/24/2017

---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog-Klasse
Ein Wrapper für eine MFC-Dialogfeldklasse, die ein Windows Forms-Benutzersteuerelement hostet.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
    public CDialog  
```  
  
#### <a name="parameters"></a>Parameter  
 `TManagedControl`  
 Die .NET Framework-Benutzersteuerelements in MFC-Anwendung angezeigt werden sollen.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Erstellt ein `CWinFormsDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Ruft einen Verweis auf das Windows Forms-Benutzersteuerelement ab.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Ruft ein Fensterhandle für das Windows Forms-Benutzersteuerelement ab.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Initialisiert die MFC-Dialogfeld erstellen und Hosten eines Windows Forms-Benutzersteuerelements auf.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsDialog::GetControl](#getcontrol) in Ausdrücken.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Wandelt ein als Verweis auf ein Windows Forms-Benutzersteuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 `CWinFormsDialog`ist ein Wrapper für eine MFC-Dialogfeldklasse ( [CDialog](../../mfc/reference/cdialog-class.md)), die ein Windows Forms-Benutzersteuerelement hostet. Dies ermöglicht die Anzeige von .NET Framework-Steuerelemente in einem MFC-Dialogfeld mit oder ohne Modus.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) und [Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>CWinFormsDialog::CWinFormsDialog  
 Erstellt ein `CWinFormsDialog`-Objekt.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDTemplate`  
 Enthält die ID der Dialogfeldvorlagen-Ressource ein Feld. Verwenden Sie den Dialog-Editor die Dialogfeldvorlage erstellen und speichern es in der Anwendung Ressourcenskriptdatei. Weitere Informationen zu Dialogfeldvorlagen finden Sie unter [CDialog-Klasse](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>CWinFormsDialog::GetControl  
 Ruft einen Verweis auf das Windows Forms-Benutzersteuerelement ab.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das Windows Forms-Steuerelement in der MFC-Dialogfeld.  
  
##  <a name="getcontrolhandle"></a>CWinFormsDialog::GetControlHandle  
 Ruft ein Fensterhandle für das Windows Forms-Benutzersteuerelement ab.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Fenster-Handle, das Windows Forms-Benutzersteuerelement zurück.  
  
##  <a name="oninitdialog"></a>CWinFormsDialog::OnInitDialog  
 Initialisiert die MFC-Dialogfeld erstellen und Hosten eines Windows Forms-Benutzersteuerelements auf.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt. Wenn `OnInitDialog` gibt einen Wert ungleich NULL, Windows legt den Eingabefokus auf das erste Steuerelement im Dialogfeld. Diese Methode kann 0 nur zurück, wenn die Anwendung explizit in das Dialogfeld den Eingabefokus auf eines der Steuerelemente festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Beim Erstellen der MFC-Dialogfeld (mithilfe der [erstellen](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), oder [DoModal](../../mfc/reference/cdialog-class.md#domodal) Methode geerbt von [CDialog](../../mfc/reference/cdialog-class.md)), eine `WM_INITDIALOG` Nachricht gesendet wird, und diese Methode wird aufgerufen. Erstellt eine Instanz eines Windows Forms-Steuerelements im Dialogfeld, und passt die Größe des Dialogfelds, um die Größe des Benutzersteuerelements gerecht zu werden. Klicken Sie dann das neue Steuerelement in der MFC-Dialogfeld gehostet.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn zur speziellen Verarbeitung bei der Initialisierung des Dialogfelds müssen. Weitere Informationen zum Verwenden dieser Methode finden Sie unter [CDialog::](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>CWinFormsDialog::operator-&gt;  
 Ersetzt [CWinFormsDialog::GetControl](#getcontrol) in Ausdrücken.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bietet eine einfache Syntax, die ersetzt `GetControl` in Ausdrücken.  
  
 Informationen zur Verwendung von Windows Forms finden Sie unter [mithilfe eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>CWinFormsDialog::operator TManagedControl ^  
 Wandelt ein als Verweis auf ein Windows Forms-Benutzersteuerelement.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator Wandelt einen Typ als Verweis auf ein Windows Forms-Steuerelement. Dient zum Übergeben einer `CWinFormsDialog<``TManagedControl``>` Dialogfeld Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement Benutzerobjekt akzeptieren.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)

