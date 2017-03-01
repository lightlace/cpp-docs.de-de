---
title: Klasse CMFCEditBrowseCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl::PreTranslateMessage method
- CMFCEditBrowseCtrl constructor
- CMFCEditBrowseCtrl class
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
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
ms.openlocfilehash: 5c5650da677a442628049c9ef4b41c2142cfb2c2
ms.lasthandoff: 02/24/2017

---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl-Klasse
Die `CMFCEditBrowseCtrl` -Klasse unterstützt das Bearbeitungssteuerelement durchsuchen, wird ein Bearbeitungsfeld, das eine Schaltfläche zum Durchsuchen enthalten. Wenn der Benutzer auf die Schaltfläche zum Durchsuchen klicken, führt das Steuerelement eine benutzerdefinierte Aktion aus oder zeigt ein Standarddialogfeld an, das einen Dateibrowser oder einen Ordnerbrowser enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Standardkonstruktor|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Aktiviert oder deaktiviert (ausgeblendet) die Schaltfläche zum Durchsuchen.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Ermöglicht die Schaltfläche zum Durchsuchen, und setzt das Steuerelement zum Bearbeiten von Durchsuchen in *Datei durchsuchen* Modus.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Ermöglicht die Schaltfläche zum Durchsuchen, und setzt das Steuerelement zum Bearbeiten von Durchsuchen in *Ordner durchsuchen* Modus.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Gibt den aktuellen Durchsuchenmodus zurück.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Wird vom Framework aufgerufen, nachdem das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wird.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Wird vom Framework aufgerufen, nachdem der Benutzer auf die Durchsuchen-Schaltfläche klickt.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Zeichnet die aktuelle Bearbeitungssteuerelement durchsuchen.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Aufgerufen, die Durchsuchen-Schaltfläche gezeichnet werden soll.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Wird vom Framework aufgerufen, wenn ein ungültiger Dateiname in das Bearbeitungssteuerelement eingegeben wurde.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Legt ein benutzerdefiniertes Bild für die Schaltfläche zum Durchsuchen.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie ein Bearbeitungssteuerelement, wählen Sie einen Datei- oder Ordnernamen ein. Verwenden Sie optional das Steuerelement wie z. B. eine benutzerdefinierte Aktion ausführen, um ein Dialogfeld anzuzeigen. Anzeigen oder die Durchsuchen-Schaltfläche nicht angezeigt werden können, und Sie können eine benutzerdefinierte Bezeichnung oder ein Bild auf die Schaltfläche anwenden.  
  
 Die *Durchsuchen-Modus* von Durchsuchen bearbeiten-Steuerelement bestimmt, ob eine Schaltfläche zum Durchsuchen angezeigt und welche Aktion tritt auf, wenn auf die Schaltfläche geklickt wird. Weitere Informationen finden Sie unter der [GetMode](#getmode) Methode.  
  
 Die `CMFCEditBrowseCtrl` Klasse unterstützt die folgenden Modi.  
  
 `custom mode`  
 Klickt der Benutzer auf die Schaltfläche zum Durchsuchen, wird eine benutzerdefinierte Aktion ausgeführt. Sie können z. B. eine anwendungsspezifische-Dialogfeld angezeigt.  
  
 `file mode`  
 Klickt der Benutzer auf die Schaltfläche zum Durchsuchen, wird ein Dialogfeld zur standard-Datei angezeigt.  
  
 `folder mode`  
 Klickt der Benutzer auf die Schaltfläche zum Durchsuchen, wird ein Dialogfeld Standardordner angezeigt.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Gewusst wie: Angeben eines Edit-Steuerelements durchsuchen  
 Führen Sie die folgenden Schritte aus, um ein Bearbeitungssteuerelement durchsuchen in Ihrer Anwendung zu integrieren:  
  
1.  Wenn Sie einen benutzerdefinierten Durchsuchenmodus implementieren möchten, leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse, und überschreiben Sie dann die [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) Methode. Führen Sie einer benutzerdefinierten Durchsuchen aus, und aktualisieren Sie das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis, in der überschriebenen Methode.  
  
2.  Betten Sie entweder die `CMFCEditBrowseCtrl` oder das Bearbeiten von abgeleiteten durchsuchen Steuerelementobjekt in das übergeordnete Fenster-Objekt.  
  
3.  Bei Verwendung der **-Klassen-Assistenten** um ein Dialogfeld zu erstellen, fügen Sie ein Edit-Steuerelement ( `CEdit`) auf das Formular. Fügen Sie außerdem eine Variable für den Zugriff auf das Steuerelement in der Headerdatei. Ändern Sie in der Headerdatei den Typ der Variablen aus `CEdit` auf `CMFCEditBrowseCtrl`. Das Steuerelement zum Bearbeiten von Durchsuchen wird automatisch erstellt. Wenn Sie nicht verwenden die **-Klassen-Assistenten**, Hinzufügen einer `CMFCEditBrowseCtrl` -Variablen in der Headerdatei und rufen Sie dann seine `Create` Methode.  
  
4.  Verwenden, wenn Sie ein Bearbeitungssteuerelement in einem Dialogfeld hinzufügen, die **ClassWizard** Tool, um den Datenaustausch einzurichten.  
  
5.  Rufen Sie die [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), oder [EnableBrowseButton](#enablebrowsebutton) Methode, um den Durchsuchenmodus festlegen und die Schaltfläche zum Durchsuchen angezeigt. Rufen Sie die [GetMode](#getmode) Methode, um den aktuellen Durchsuchenmodus zu erhalten.  
  
6.  Um ein benutzerdefiniertes Bild für die Schaltfläche zum Durchsuchen bereitzustellen, rufen die [SetBrowseButtonImage](#setbrowsebuttonimage) -Methode oder außer Kraft setzen der [OnDrawBrowseButton](#ondrawbrowsebutton) Methode.  
  
7.  Um die Schaltfläche zum Durchsuchen von Bearbeitungssteuerelement durchsuchen zu entfernen, rufen die [EnableBrowseButton](#enablebrowsebutton) -Methode mit der `bEnable` Parametersatz zu `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zwei Methoden in der `CMFCEditBrowseCtrl` Klasse: `EnableFolderBrowseButton` und `EnableFileBrowseButton`. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&6;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#7;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxeditbrowsectrl.h  
  
##  <a name="a-nameenablebrowsebuttona--cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Zeigt oder die Schaltfläche zum Durchsuchen nicht auf das aktuelle durchsuchen Bearbeitungssteuerelement angezeigt.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 `TRUE`auf die Schaltfläche zum Durchsuchen angezeigt werden. `FALSE` nicht auf die Schaltfläche zum Durchsuchen angezeigt. Der Standardwert ist `TRUE`.  
  
 `szLabel`  
 Die Bezeichnung, die auf die Schaltfläche zum Durchsuchen angezeigt wird. Der Standardwert ist " **... **".  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `bEnable` Parameter ist `TRUE`, implementieren Sie eine benutzerdefinierte Aktion ausführen, wenn die Durchsuchen-Schaltfläche geklickt wird. Um eine benutzerdefinierte Aktion zu implementieren, leiten Sie eine Klasse von der `CMFCEditBrowseCtrl` Klasse, und überschreiben Sie dann die [OnBrowse](#onbrowse) Methode.  
  
 Wenn die `bEnable` Parameter ist `TRUE`, ist der Durchsuchen-Modus des Steuerelements `BrowseMode_Default`ist, andernfalls der Durchsuchenmodus ist `BrowseMode_None`. Weitere Informationen zum Durchsuchen-Modus finden Sie unter der [GetMode](#getmode) Methode.  
  
##  <a name="a-nameenablefilebrowsebuttona--cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Zeigt die Schaltfläche zum Durchsuchen auf das aktuelle Steuerelement zum Bearbeiten durchsuchen und setzt das Steuerelement in *Datei durchsuchen* Modus.  
  
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
  
##  <a name="a-nameenablefolderbrowsebuttona--cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Zeigt die Schaltfläche zum Durchsuchen auf das aktuelle Steuerelement zum Bearbeiten durchsuchen und setzt das Steuerelement in *Ordner durchsuchen* Modus.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Steuerelement zum Bearbeiten von Durchsuchen im Ordner Durchsuchen-Modus und der Benutzer klickt auf die Schaltfläche zum Durchsuchen, zeigt das Steuerelement das Dialogfeld Auswahl Standardordner.  
  
##  <a name="a-namegetmodea--cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Ruft das Durchsuchen des aktuellen durchsuchen Bearbeitungssteuerelements ab.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der Enumerationswerte, der den aktuellen Modus des Bearbeitungspunktes gibt durchsuchen Steuerelement. Durchsuchenmodus bestimmt, ob das Framework die Schaltfläche zum Durchsuchen angezeigt wird und welche Aktion tritt auf, wenn ein Benutzer auf die Schaltfläche klickt.  
  
 In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. Eine Programmierer definierte Aktion wird ausgeführt.|  
|`BrowseMode_File`|`file mode`. Das standardmäßige-Browser-Dialogfeld wird angezeigt.|  
|`BrowseMode_Folder`|`folder mode`. Der Standardordner Browser-Dialogfeld wird angezeigt.|  
|`BrowseMode_None`|Die Schaltfläche "Durchsuchen" wird nicht angezeigt.|  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung eine `CMFCEditBrowseCtrl` Objekt wird initialisiert, `BrowseMode_None` Modus. Ändern Sie den Durchsuchenmodus mit der [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), und [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton) Methoden.  
  
##  <a name="a-nameonafterupdatea--cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Wird vom Framework aufgerufen, nachdem das Steuerelement zum Bearbeiten von Durchsuchen mit dem Ergebnis einer Aktion "Durchsuchen" aktualisiert wird.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse eine benutzerdefinierte Aktion implementiert.  
  
##  <a name="a-nameonbrowsea--cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Vom Framework aufgerufen, nachdem der Benutzer auf die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen klickt.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um benutzerdefinierten Code auszuführen, klickt der Benutzer auf die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen. Leiten Sie eine eigene Klasse von der `CMFCEditBrowseCtrl` Klasse, und überschreiben die `OnBrowse` Methode. Implementieren Sie in dieser Methode eine benutzerdefinierte durchsuchen-Aktion, und aktualisieren Sie optional im Textfeld des Bearbeitungssteuerelements durchsuchen. In der Anwendung verwendet die [EnableBrowseButton](#enablebrowsebutton) durchsuchen Bearbeitungssteuerelement Übernahme *benutzerdefinierte Durchsuchen* Modus.  
  
##  <a name="a-nameonchangelayouta--cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Zeichnet die aktuelle Bearbeitungssteuerelement durchsuchen.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn die Durchsuchen-Modus Bearbeiten Suchen-Steuerelements geändert wird. Weitere Informationen finden Sie unter [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="a-nameondrawbrowsebuttona--cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Aufgerufen, um die Schaltfläche zum Durchsuchen auf das Steuerelement zum Bearbeiten von durchsuchen zu zeichnen.  
  
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
 Das umschließende Rechteck der Schaltfläche Durchsuchen.  
  
 `bIsButtonPressed`  
 `TRUE`Wenn die Maustaste gedrückt wird; andernfalls `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`Wenn die Schaltfläche hervorgehoben ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion in einer abgeleiteten Klasse zum Anpassen der Darstellung der Schaltfläche Durchsuchen.  
  
##  <a name="a-namesetbrowsebuttonimagea--cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Legt ein benutzerdefiniertes Abbild auf die Schaltfläche zum Durchsuchen des Bearbeitungssteuerelements durchsuchen.  
  
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
 Verwenden Sie diese Methode, um ein benutzerdefiniertes Bild auf die Schaltfläche zum Durchsuchen anzuwenden. Standardmäßig erhält das Framework ein Standardabbilds wird das Steuerelement zum Bearbeiten von Durchsuchen in *Datei durchsuchen* oder *Ordner durchsuchen* Modus.  
  
##  <a name="a-nameonillegalfilenamea--cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Wird vom Framework aufgerufen, wenn ein ungültiger Dateiname in das Bearbeitungssteuerelement eingegeben wurde.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Parameter  
 `strFileName`  
 Gibt den Dateinamen für die ungültige.  
  
### <a name="return-value"></a>Rückgabewert  
 Sollte zurückgeben `FALSE` , wenn der Dateiname nicht weiter im Dateidialogfeld übergeben werden kann. In diesem Fall den Fokus wieder auf das Bearbeitungssteuerelement festgelegt ist und der Benutzer sollte weiter bearbeiten. Die standardmäßige Implementierung zeigt ein Meldungsfeld, das dem Benutzer mitteilt, zu der ungültige Dateiname und gibt `FALSE`. Sie können diese Methode überschreiben, korrigieren Sie den Dateinamen und zurückgeben `TRUE` zur weiteren Verarbeitung.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

