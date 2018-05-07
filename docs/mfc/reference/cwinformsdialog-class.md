---
title: CWinFormsDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7596140f48b62a63189444bee6fb363552766fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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
 Das .NET Framework-Benutzersteuerelement in der MFC-Anwendung angezeigt werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](#cwinformsdialog)|Erstellt ein `CWinFormsDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](#getcontrol)|Ruft einen Verweis auf das Windows Forms-Benutzersteuerelement ab.|  
|[CWinFormsDialog::GetControlHandle](#getcontrolhandle)|Ruft ein Fensterhandle für das Windows Forms-Benutzersteuerelement ab.|  
|[CWinFormsDialog::OnInitDialog](#oninitdialog)|Initialisiert die MFC-Dialogfeld erstellen und Hosten eines Windows Forms-Benutzersteuerelements darauf.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|name||  
|----------|-|  
|[CWinFormsDialog::operator-&gt;](#operator_-_gt)|Ersetzt [CWinFormsDialog::GetControl](#getcontrol) in Ausdrücken.|  
|[CWinFormsDialog::operator TManagedControl ^](#operator_tmanagedcontrol)|Wandelt einen Typ ein Verweis auf ein Windows Forms-Benutzersteuerelement.|  
  
## <a name="remarks"></a>Hinweise  
 `CWinFormsDialog` ist ein Wrapper für eine MFC-Dialogfeldklasse ( [CDialog](../../mfc/reference/cdialog-class.md)), die ein Windows Forms-Benutzersteuerelement hostet. Dies ermöglicht die Anzeige von .NET Framework-Steuerelemente in einem MFC-Dialogfeld mit oder ohne Modus.  
  
 Weitere Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) und [Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwinforms.h  
  
##  <a name="cwinformsdialog"></a>  CWinFormsDialog::CWinFormsDialog  
 Erstellt ein `CWinFormsDialog`-Objekt.  
  
```  
CWinFormsDialog(UINT nIDTemplate = IDD);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDTemplate`  
 Enthält die ID der Dialogfeldvorlagen-Ressource ein Feld an. Verwenden Sie den Dialog-Editor, um der Dialogfeldvorlage erstellen und speichern es in der Anwendung Ressourcenskriptdatei. Weitere Informationen zu Dialogfeldvorlagen, finden Sie unter [CDialog-Klasse](../../mfc/reference/cdialog-class.md).  
  
##  <a name="getcontrol"></a>  CWinFormsDialog::GetControl  
 Ruft einen Verweis auf das Windows Forms-Benutzersteuerelement ab.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das Windows Forms-Steuerelement in der MFC-Dialogfeld zurück.  
  
##  <a name="getcontrolhandle"></a>  CWinFormsDialog::GetControlHandle  
 Ruft ein Fensterhandle für das Windows Forms-Benutzersteuerelement ab.  
  
```  
inline HWND GetControlHandle() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Fensterhandle auf das Windows Forms-Benutzersteuerelement zurück.  
  
##  <a name="oninitdialog"></a>  CWinFormsDialog::OnInitDialog  
 Initialisiert die MFC-Dialogfeld erstellen und Hosten eines Windows Forms-Benutzersteuerelements darauf.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde. Wenn `OnInitDialog` ungleich NULL zurückgegeben wird, Windows legt den Eingabefokus auf das erste Steuerelement im Dialogfeld. Diese Methode kann 0 zurückgeben, nur dann, wenn die Anwendung explizit den Eingabefokus eines der Steuerelemente im Dialogfeld festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die MFC-Dialogfeld erstellt wird (mithilfe der [erstellen](../../mfc/reference/cdialog-class.md#create), [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect), oder [DoModal](../../mfc/reference/cdialog-class.md#domodal) Methode geerbt von [CDialog](../../mfc/reference/cdialog-class.md)), eine `WM_INITDIALOG` Nachricht gesendet wird, und diese Methode wird aufgerufen. Erstellt eine Instanz eines Windows Forms-Steuerelements im Dialogfeld, und passt die Größe des Dialogfelds, um die Größe des Benutzersteuerelements Rechnung zu tragen. Klicken Sie dann hostet das neue Steuerelement in der MFC-Dialogfeld.  
  
 Überschreiben Sie diese Memberfunktion auf, wenn besondere Verarbeitung bei der Initialisierung des Dialogfelds "" ausführen müssen. Weitere Informationen zum Verwenden dieser Methode finden Sie unter [CDialog::](../../mfc/reference/cdialog-class.md#oninitdialog).  
  
##  <a name="operator_-_gt"></a>  CWinFormsDialog::operator-&gt;  
 Ersetzt [CWinFormsDialog::GetControl](#getcontrol) in Ausdrücken.  
  
```  
inline TManagedControl^  operator->() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator bietet eine einfache Syntax, die ersetzt `GetControl` in Ausdrücken.  
  
 Informationen zur Verwendung von Windows Forms finden Sie unter [Verwenden eines Windows Form-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol_xor"></a>  CWinFormsDialog::operator TManagedControl ^  
 Wandelt einen Typ ein Verweis auf ein Windows Forms-Benutzersteuerelement.  
  
```  
inline operator TManagedControl^() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator Wandelt einen Typ ein Verweis auf ein Windows Forms-Steuerelement. Es wird zum Übergeben einer `CWinFormsDialog<TManagedControl>` (Dialogfeld), Funktionen, die einen Zeiger auf ein Windows Forms-Steuerelement Benutzerobjekt akzeptieren.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView-Klasse](../../mfc/reference/cwinformsview-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
