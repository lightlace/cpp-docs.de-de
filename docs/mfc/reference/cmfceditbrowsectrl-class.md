---
title: CMFCEditBrowseCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de1e30e6ca9f404199c6db43837f35d612a02b69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl-Klasse
Die `CMFCEditBrowseCtrl` Klasse unterstützt das Bearbeitungssteuerelement durchsuchen, also ein Bearbeitungsfeld, das eine Schaltfläche zum Durchsuchen optional enthält. Wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken, führt das Steuerelement eine benutzerdefinierte Aktion aus oder zeigt ein Standarddialogfeld an, das einen Dateibrowser oder einen Ordnerbrowser enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Standardkonstruktor|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Aktiviert oder deaktiviert (ausgeblendet) die Schaltfläche zum Durchsuchen.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Aktiviert die Schaltfläche zum Durchsuchen und setzt das Durchsuchen Bearbeitungssteuerelement in *Datei durchsuchen* Modus.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Aktiviert die Schaltfläche zum Durchsuchen und setzt das Durchsuchen Bearbeitungssteuerelement in *Ordner durchsuchen* Modus.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Gibt den aktuellen Durchsuchenmodus zurück.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Vom Framework aufgerufen, nachdem das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wird.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Vom Framework aufgerufen, nachdem der Benutzer die Schaltfläche zum Durchsuchen klicken.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Zeichnet die aktuelle Bearbeitungssteuerelement durchsuchen.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Wird aufgerufen, durch das Framework die Durchsuchen-Schaltfläche gezeichnet werden soll.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Wird vom Framework aufgerufen, wenn ein ungültiger Dateiname in das Bearbeitungssteuerelement eingegeben wurde.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Legt ein benutzerdefiniertes Bild für die Schaltfläche zum Durchsuchen.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie ein Bearbeitungssteuerelement für das Durchsuchen, wählen Sie einen Datei- oder Ordnernamen ein. Verwenden Sie optional das Steuerelement, z. B. eine benutzerdefinierte Aktion ausführen, um ein Dialogfeld anzuzeigen. Können Sie anzeigen oder die Schaltfläche zum Durchsuchen angezeigt, und Sie können eine benutzerdefinierte Bezeichnung oder ein Bild anwenden, auf die Schaltfläche.  
  
 Die *Durchsuchenmodus* der Bearbeiten Suchen Steuerelement bestimmt, ob eine Schaltfläche zum Durchsuchen angezeigt und welche Aktion tritt auf, wenn die Schaltfläche geklickt wird. Weitere Informationen finden Sie unter der [GetMode](#getmode) Methode.  
  
 Die `CMFCEditBrowseCtrl` Klasse unterstützt die folgenden Modi.  
  
 `custom mode`  
 Eine benutzerdefinierte Aktion wird ausgeführt, wenn der Benutzer die Schaltfläche zum Durchsuchen klickt. Sie können z. B. eine anwendungsspezifische-Dialogfeld angezeigt.  
  
 `file mode`  
 Eine standardmäßige Dialogfeld zur Dateiauswahl wird angezeigt, wenn der Benutzer die Schaltfläche zum Durchsuchen klickt.  
  
 `folder mode`  
 Eine standardmäßige Auswahl (Dialogfeld) wird angezeigt, wenn der Benutzer die Schaltfläche zum Durchsuchen klicken.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Gewusst wie: Geben Sie ein Bearbeitungssteuerelement für Durchsuchen  
 Führen Sie die folgenden Schritte aus, um ein Bearbeitungssteuerelement zum Durchsuchen, in der Anwendung zu integrieren:  
  
1.  Wenn Sie einen benutzerdefinierten Durchsuchenmodus implementieren möchten, leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse, und klicken Sie dann überschreiben die [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) Methode. Führen Sie in der überschriebenen Methode eine benutzerdefinierte Aktion durchsuchen, und aktualisieren Sie das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis.  
  
2.  Betten Sie entweder die `CMFCEditBrowseCtrl` Objekt oder abgeleiteten bearbeiten durchsuchen-Control-Objekt in das übergeordnete Fenster-Objekt.  
  
3.  Bei Verwendung der **Klassen-Assistent** um ein Dialogfeld zu erstellen, fügen Sie ein Bearbeitungssteuerelement ( `CEdit`) auf dem Formular des Dialogfelds. Darüber hinaus fügt eine Variable für den Zugriff auf das Steuerelement in der Headerdatei. Ändern Sie in der Headerdatei den Typ der Variablen aus `CEdit` auf `CMFCEditBrowseCtrl`. Das Steuerelement zum Bearbeiten von Durchsuchen wird automatisch erstellt werden. Wenn Sie nicht verwenden die **Klassen-Assistent**, Hinzufügen einer `CMFCEditBrowseCtrl` Variable auf die Headerdatei und rufen Sie dann seine `Create` Methode.  
  
4.  Wenn Sie ein Bearbeitungssteuerelement für das Navigieren zu einem Dialogfeld hinzufügen, verwenden Sie die **ClassWizard** Tool zum Datenaustausch einrichten.  
  
5.  Rufen Sie die [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), oder [EnableBrowseButton](#enablebrowsebutton) Methode, um den Durchsuchenmodus festgelegt und die Schaltfläche zum Durchsuchen angezeigt. Rufen Sie die [GetMode](#getmode) Methode, um den aktuellen Durchsuchenmodus abzurufen.  
  
6.  Rufen Sie zum Bereitstellen eines benutzerdefinierten Abbilds für die Schaltfläche zum Durchsuchen der [SetBrowseButtonImage](#setbrowsebuttonimage) -Methode oder Überschreibung der [OnDrawBrowseButton](#ondrawbrowsebutton) Methode.  
  
7.  Rufen Sie zum Entfernen der Schaltfläche zum Durchsuchen von Bearbeitungssteuerelements zum Durchsuchen der [EnableBrowseButton](#enablebrowsebutton) Methode mit der `bEnable` Parametersatz auf `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zwei Methoden in der `CMFCEditBrowseCtrl` Klasse: `EnableFolderBrowseButton` und `EnableFileBrowseButton`. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Zeigt an, oder die Schaltfläche zum Durchsuchen nicht auf das aktuelle Steuerelement zum Bearbeiten zum Durchsuchen angezeigt.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 `TRUE`auf die Schaltfläche zum Durchsuchen angezeigt. `FALSE` nicht auf die Schaltfläche zum Durchsuchen angezeigt. Der Standardwert ist `TRUE`.  
  
 `szLabel`  
 Die Bezeichnung, die auf die Schaltfläche zum Durchsuchen angezeigt wird. Der Standardwert ist " **...** ".  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `bEnable` Parameter ist `TRUE`, implementieren Sie eine benutzerdefinierte Aktion ausführen, wenn die Durchsuchen-Schaltfläche geklickt wird. Um eine benutzerdefinierte Aktion zu implementieren, leiten Sie eine Klasse von der `CMFCEditBrowseCtrl` Klasse, und klicken Sie dann überschreiben die [OnBrowse](#onbrowse) Methode.  
  
 Wenn die `bEnable` Parameter ist `TRUE`, ist die Durchsuchen-Modus des Steuerelements `BrowseMode_Default`ist, andernfalls der Durchsuchenmodus ist `BrowseMode_None`. Weitere Informationen zum von Durchsuchenmodi finden Sie unter der [GetMode](#getmode) Methode.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Zeigt die Schaltfläche zum Durchsuchen für das aktuelle Steuerelement zum Bearbeiten durchsuchen und versetzt das Steuerelement in *Datei durchsuchen* Modus.  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDefExt`  
 Gibt die Standard-Dateierweiterung an, die im Dialogfeld zur Dateiauswahl verwendet wird. Der Standardwert ist `NULL`.  
  
 `lpszFilter`  
 Gibt die Standardfilterzeichenfolge an, die im Dialogfeld zur Dateiauswahl verwendet wird. Der Standardwert ist `NULL`.  
  
 `dwFlags`  
 Dialogfeldflags. Der Standardwert ist eine bitweise Kombination (OR) von OFN_HIDEREADONLY und OFN_OVERWRITEPROMPT.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement zum Bearbeiten und Durchsuchen sich im Dateidurchsuchungsmodus befindet und der Benutzer auf die Schaltfläche zum Durchsuchen klickt, zeigt das Steuerelement das standardmäßige Dialogfeld zur Dateiauswahl an.  
  
 Eine vollständige Liste der verfügbaren Flags finden Sie unter [OPENFILENAME-Struktur](https://msdn.microsoft.com/library/ms646839.aspx).  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Zeigt die Schaltfläche zum Durchsuchen für das aktuelle Steuerelement zum Bearbeiten durchsuchen und versetzt das Steuerelement in *Ordner durchsuchen* Modus.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement zum Bearbeiten von Durchsuchen im Ordner Durchsuchen-Modus und der Benutzer klickt auf die Schaltfläche zum Durchsuchen, zeigt das Steuerelement im Standardordner-Auswahldialogfeld.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Ruft ab den Durchsuchenmodus des aktuellen Edit-Steuerelements zum Durchsuchen.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der Enumerationswerte, der angibt, die der aktuelle Modus der Bearbeitung durchsuchen Steuerelement. Die Durchsuchen-Modus bestimmt, ob das Framework die Schaltfläche zum Durchsuchen angezeigt wird und welche Aktion tritt auf, wenn ein Benutzer die Schaltfläche klickt.  
  
 In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode` Eine Programmierer definierte Aktion ausgeführt wird.|  
|`BrowseMode_File`|`file mode` Das standard-Datei-Browser-Dialogfeld wird angezeigt.|  
|`BrowseMode_Folder`|`folder mode` Der Standardordner-Browser-Dialogfeld wird angezeigt.|  
|`BrowseMode_None`|Die Schaltfläche zum Durchsuchen, wird nicht angezeigt.|  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig ein `CMFCEditBrowseCtrl` -Objekt initialisiert wird, um `BrowseMode_None` Modus. Ändern Sie den Durchsuchenmodus mit der [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), und [CMFCEditBrowseCtrl::EnableFolderBrowseButton ](#enablefolderbrowsebutton) Methoden.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Vom Framework aufgerufen, nachdem das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wird.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Implementieren einer benutzerdefinierten Aktion.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Vom Framework aufgerufen, nachdem der Benutzer die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements zum Durchsuchen klickt.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um benutzerdefinierten Code ausführen, wenn der Benutzer die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements zum Durchsuchen klickt. Leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse, und überschreiben die `OnBrowse` Methode. Implementieren Sie in dieser Methode eine benutzerdefinierte Aktion durchsuchen, und aktualisieren Sie optional im Textfeld des Bearbeitungssteuerelements zum Durchsuchen. Verwenden Sie in der Anwendung die [EnableBrowseButton](#enablebrowsebutton) Methode, um das Steuerelement zum Bearbeiten von Durchsuchen gelagerte *benutzerdefinierte Durchsuchen* Modus.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Zeichnet die aktuelle Bearbeitungssteuerelement durchsuchen.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn Änderungen Einfluss auf die Durchsuchen-Modus die Durchsuchen-bearbeiten. Weitere Informationen finden Sie unter [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Wird aufgerufen, durch das Framework die Schaltfläche zum Durchsuchen für das Steuerelement zum Bearbeiten von Durchsuchen gezeichnet werden soll.  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 `Rect`  
 Das Begrenzungsrechteck der Schaltfläche zum Durchsuchen.  
  
 `bIsButtonPressed`  
 `TRUE`Wenn die Schaltfläche aufgerufen werden; andernfalls `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`Wenn die Schaltfläche hervorgehoben ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Anpassen der Darstellung der Schaltfläche zum Durchsuchen.  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Legt ein benutzerdefiniertes Image auf die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements zum Durchsuchen.  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>Parameter  
 `hIcon`  
 Das Handle eines Symbols.  
  
 `hBitmap`  
 Das Handle einer Bitmap.  
  
 `uiBmpResId`  
 Die Ressourcen-ID einer Bitmap.  
  
 `bAutoDestroy`  
 `TRUE`So löschen Sie das angegebene Symbol oder eine Bitmap, wenn diese Methode beendet wird; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um ein benutzerdefiniertes Image auf die Schaltfläche zum Durchsuchen anzuwenden. Standardmäßig erhält das Framework ein Standardimage, wenn das Steuerelement zum Bearbeiten von Durchsuchen wird *Datei durchsuchen* oder *Ordner durchsuchen* Modus.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Wird vom Framework aufgerufen, wenn ein ungültiger Dateiname in das Bearbeitungssteuerelement eingegeben wurde.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `strFileName`  
 Gibt den Dateinamen nicht zulässig.  
  
### <a name="return-value"></a>Rückgabewert  
 Sollte zurückgeben `FALSE` , wenn der Dateiname nicht verbindungsmöglichkeiten mit dem Dialogfeld "Datei" übergeben werden kann. In diesem Fall den Fokus wieder auf das Bearbeitungssteuerelement festgelegt ist, und der Benutzer sollte weiterhin bearbeiten. Die standardmäßige Implementierung zeigt ein Meldungsfeld darüber informiert, dass hinsichtlich des Dateinamens nicht zulässig, und gibt `FALSE`. Sie können überschreiben Sie diese Methode, korrigieren Sie den Dateinamen, und `TRUE` zur weiteren Verarbeitung.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
