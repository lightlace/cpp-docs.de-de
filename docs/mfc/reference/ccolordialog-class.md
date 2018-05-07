---
title: CColorDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3888f054baab61bb7422403b0766d7f757914d1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ccolordialog-class"></a>CColorDialog-Klasse
Bietet die Möglichkeit, ein Farbauswahl Dialogfeld in die Anwendung integrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Erstellt ein `CColorDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Zeigt das Dialogfeld Farbe und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CColorDialog::GetColor](#getcolor)|Gibt eine **COLORREF** Struktur mit den Werten der ausgewählten Farbe.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Ruft benutzerdefinierte Farben, die vom Benutzer erstellten ab.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Erzwingt, dass die aktuelle Farbauswahl an der angegebenen Farbe.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|Außer Kraft setzen Sie, um zu überprüfen, ob die Farbe, die in das Dialogfeld eingegeben haben.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|Eine Struktur, die zum Anpassen der Einstellungen des Dialogfelds verwendet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CColorDialog` Objekt wird ein Dialogfeld mit einer Liste von Farben, die für die Anzeigesystem definiert sind. Die Benutzer kann auswählen, oder erstellen eine bestimmte Farbe aus der Liste, der wieder dann an die Anwendung gemeldet wird, wenn das Dialogfeld beendet wird.  
  
 So erstellen Sie eine `CColorDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor oder leiten Sie eine neue Klasse und Ihre eigenen benutzerdefinierten Konstruktor verwenden.  
  
 Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_cc](#m_cc) Struktur der Werte von Steuerelementen für das Dialogfeld zu initialisieren. Die `m_cc` Struktur ist vom Typ [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 Rufen Sie nach dem initialisieren das Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglicht dem Benutzer eine Farbe auszuwählen. `DoModal` Gibt die Auswahl des Benutzers entweder das Dialogfeld OK ( **IDOK**) oder "Abbrechen" ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, können Sie eine der `CColorDialog`des Memberfunktionen zum Abrufen von Informationen vom Benutzer eingegeben.  
  
 Sie können die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) -Funktion zu bestimmen, ob der Fehler während der Initialisierung des Dialogfelds und erfahren Sie mehr über den Fehler.  
  
 `CColorDialog` basiert auf der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher ausgeliefert wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CColorDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten mit der Basisklasse übergeben werden.  
  
 Anpassen von die Hookfunktion ist nicht erforderlich.  
  
> [!NOTE]
>  Bei einigen Installationen der `CColorDialog` Objekt wird nicht mit grauem Hintergrund angezeigt, wenn Sie das Framework, zum Ausführen weiterer verwendet haben `CDialog` Objekte grau.  
  
 Weitere Informationen zur Verwendung von `CColorDialog`, finden Sie unter [Standarddialogfeld-Klassen](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog  
 Erstellt ein `CColorDialog`-Objekt.  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *clrInit*  
 Die Standardauswahl für die Farbe. Wenn kein Wert angegeben wird, ist die Standardeinstellung RGB(0,0,0) (Schwarz).  
  
 `dwFlags`  
 Ein Satz von Flags, die die Funktion und die Darstellung des Dialogfelds anpassen. Weitere Informationen finden Sie unter der [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) Struktur im Windows SDK.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld über- oder Besitzer Fenster.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CColorDialog::DoModal  
 Mit dieser Funktion wird für die Anzeige von der Windows allgemeine Farbe (Dialogfeld), und ermöglicht dem Benutzer eine Farbe auszuwählen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um festzustellen, ob ein Fehler aufgetreten.  
  
 **IDOK** und **IDCANCEL** sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder "Abbrechen" ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Farben im Dialogfeld Optionen zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cc](#m_cc) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal` aber erst, nachdem das Dialogfeld-Objekt erstellt wird.  
  
 Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="getcolor"></a>  CColorDialog::GetColor  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen von Informationen zu den vom Benutzer ausgewählten Farbe.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die RGB-Informationen für die Farbe ausgewählt, die im Dialogfeld "Farbe" enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors  
 `CColorDialog` -Objekte ermöglichen es dem Benutzer, zusätzlich zur Auswahl von Farben, um bis zu 16 benutzerdefinierte Farben zu definieren.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array von 16 RGB-Farbwerte, die benutzerdefinierte Farben, die vom Benutzer erstellten speichert.  
  
### <a name="remarks"></a>Hinweise  
 Die `GetSavedCustomColors` methodenmemberfunktion bietet Zugriff auf diese Farben. Diese Farben können abgerufen werden, nachdem [DoModal](#domodal) gibt **IDOK**.  
  
 Die 16 RGB-Werte im zurückgegebenen Array wird mit RGB(255,255,255) (weiß) initialisiert. Die benutzerdefinierten Farben, die vom Benutzer ausgewählt wurde, werden nur zwischen Dialogfeld Feld Aufrufe innerhalb der Anwendung gespeichert. Wenn Sie diese Farben zwischen den Aufrufen der Anwendung speichern möchten, müssen speichern Sie diese auf eine andere Weise, wie z. B. in einer Initialisierung (. INI)-Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>  CColorDialog::m_cc  
 Eine Struktur des Typs [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), deren Mitglieder zu speichern, die Merkmale und die Werte im Dialogfeld.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CColorDialog` -Objekt können Sie `m_cc` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>  CColorDialog::OnColorOK  
 Außer Kraft setzen Sie, um zu überprüfen, ob die Farbe, die in das Dialogfeld eingegeben haben.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld nicht geschlossen werden soll; andernfalls 0, akzeptieren die Farbe, die eingegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion nur, wenn Sie möchten benutzerdefinierte Validierung der Farbe angeben, die der Benutzer im Dialogfeld "Farbe" auswählt.  
  
 Der Benutzer kann durch eines der beiden folgenden Methoden eine Farbe auswählen:  
  
-   Klicken Sie auf eine Farbe auf der Farbpalette. RGB-Werte für die ausgewählte Farbe werden dann in die entsprechenden RGB-Bearbeitungsfelder wiedergegeben.  
  
-   Eingabe von Werten in den RGB-Bearbeitungsfelder  
  
 Überschreiben von `OnColorOK` können Sie eine Farbe Ablehnen der Benutzer ein Standarddialogfeld Farbe Einstellungsbereich anwendungsspezifische gibt.  
  
 Normalerweise müssen Sie nicht diese Funktion verwenden, da das Framework standardüberprüfung von Farben bietet und zeigt ein Meldungsfenster an, wenn eine ungültige Farbe eingegeben wird.  
  
 Sie erreichen [SetCurrentColor](#setcurrentcolor) innerhalb `OnColorOK` ein Farbauswahl zu erzwingen. Einmal `OnColorOK` wurde ausgelöst wurde (d. h. der Benutzer klickt auf **OK** Farbe akzeptieren), können Sie aufrufen [GetColor](#getcolor) zum Abrufen des RGB-Wertes, der die neu ausgewählte Farbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` erzwingen Sie die aktuelle Farbauswahl auf Farbwert in angegebenen `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird von einem Message-Handler aufgerufen oder `OnColorOK`. Das Dialogfeld aktualisiert automatisch die Auswahl des Benutzers anhand des Werts von der `clr` Parameter.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

