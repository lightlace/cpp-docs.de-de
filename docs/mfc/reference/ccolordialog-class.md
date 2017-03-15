---
title: CColorDialog Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CColorDialog
dev_langs:
- C++
helpviewer_keywords:
- colors, dialog box
- dialog boxes, colors
- CColorDialog class
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
caps.latest.revision: 25
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
ms.openlocfilehash: a8aee088aadbca18acda348c574c8f4b55d1ecbb
ms.lasthandoff: 02/24/2017

---
# <a name="ccolordialog-class"></a>CColorDialog-Klasse
Können Sie ein Dialogfeld für die Farbauswahl in Ihre Anwendung integrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|Erstellt ein `CColorDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|Zeigt ein Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CColorDialog::GetColor](#getcolor)|Gibt eine **COLORREF** Struktur, die die Werte der ausgewählten Farbe.|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|Ruft benutzerdefinierte Farben, die vom Benutzer erstellt wurden.|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|Erzwingt, dass die aktuelle Auswahl auf die angegebene Farbe.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|Überschreiben Sie, um die Farbe, die in das Dialogfeld eingegeben überprüfen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|Eine Struktur, die Einstellungen im Dialogfeld Anpassen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CColorDialog` -Objekt ist ein Dialogfeld mit einer Liste von Farben, die für die Anzeigesystem definiert sind. Der Benutzer kann auswählen, oder erstellen eine bestimmte Farbe aus der Liste, die dann an die Anwendung beim Beenden des Dialogfelds zurückgemeldet wird.  
  
 Erstellt ein `CColorDialog` Objekt verwenden Sie den bereitgestellten Konstruktor oder eine neue Klasse ableiten und Ihre eigenen benutzerdefinierten Konstruktor.  
  
 Nachdem das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_cc](#m_cc) Struktur, um die Werte der Steuerelemente des Dialogfelds zu initialisieren. Die `m_cc` Struktur ist vom Typ [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830).  
  
 Rufen Sie nach dem initialisieren das Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, eine Farbe auszuwählen. `DoModal`Gibt die Benutzerauswahl entweder das Dialogfeld OK ( **IDOK**) oder Abbrechen ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, verwenden Sie eine der `CColorDialog`Member-Funktionen zum Abrufen von Informationen vom Benutzer eingeben.  
  
 Verwenden Sie die Fenster [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) -Funktion zu bestimmen, ob Fehler während der Initialisierung des Dialogfelds und Weitere Informationen zu dem Fehler.  
  
 `CColorDialog`Abhängig von der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher enthalten ist.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CColorDialog`, geben Sie eine benutzerdefinierte Vorlage und fügen Sie eine Zuordnung Nachricht, um die Benachrichtigung über die erweiterte Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übergeben werden.  
  
 Es ist nicht erforderlich, die Hookfunktion anpassen.  
  
> [!NOTE]
>  Bei einigen Installationen der `CColorDialog` Objekt wird nicht mit einem grauen Hintergrund angezeigt, wenn Sie das Framework verwendet haben, für andere `CDialog` Objekte grau.  
  
 Weitere Informationen zur Verwendung von `CColorDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="a-nameccolordialoga--ccolordialogccolordialog"></a><a name="ccolordialog"></a>CColorDialog::CColorDialog  
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
 Ein Satz von Flags, die die Funktion und die Darstellung des Dialogfelds anpassen. Weitere Informationen finden Sie unter der [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld übergeordnete Fenster oder das Besitzer.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView Nr.&49;](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="a-namedomodala--ccolordialogdomodal"></a><a name="domodal"></a>CColorDialog::DoModal  
 Rufen Sie diese Funktion zeigt das Dialogfeld allgemeine Farbe Windows und dem Benutzer ermöglichen, eine Farbe auszuwählen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
 **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Farben im Dialogfeld Optionen zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cc](#m_cc) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal` aber erst, nachdem das Dialogfeld-Objekt erstellt wird.  
  
 Nach dem Aufruf von `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CColorDialog::CColorDialog](#ccolordialog).  
  
##  <a name="a-namegetcolora--ccolordialoggetcolor"></a><a name="getcolor"></a>CColorDialog::GetColor  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zum Abrufen von Informationen zu den vom Benutzer ausgewählten Farbe.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die RGB-Informationen für die im Dialogfeld "Farbe" ausgewählte Farbe enthält.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#50;](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="a-namegetsavedcustomcolorsa--ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>CColorDialog::GetSavedCustomColors  
 `CColorDialog`-Objekte ermöglichen es dem Benutzer, zusätzlich zur Auswahl von Farben bis zu 16 benutzerdefinierte Farben definieren.  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein Array von 16 RGB-Farbwerte, benutzerdefinierte Farben, die vom Benutzer erstellten speichert.  
  
### <a name="remarks"></a>Hinweise  
 Der `GetSavedCustomColors` Member-Funktion ermöglicht den Zugriff auf diese Farben. Diese Farben abgerufen werden können, nach [DoModal](#domodal) gibt **IDOK**.  
  
 Alle 16 RGB-Werte im zurückgegebenen Array wird mit RGB(255,255,255) (weiß) initialisiert. Die benutzerdefinierten Farben, die vom Benutzer ausgewählten werden nur zwischen Dialogfeld Feld Aufrufe innerhalb der Anwendung gespeichert. Wenn Sie diese Farben zwischen den Aufrufen der Anwendung speichern möchten, müssen speichern Sie diese auf andere Weise, wie z. B. in einer Initialisierung (. INI)-Datei.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&51;](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="a-namemcca--ccolordialogmcc"></a><a name="m_cc"></a>CColorDialog::m_cc  
 Eine Struktur vom Typ [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830), speichern, deren Mitglieder, die Eigenschaften und Werte im Dialogfeld.  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CColorDialog` -Objekt können Sie `m_cc` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#53;](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="a-nameoncoloroka--ccolordialogoncolorok"></a><a name="oncolorok"></a>CColorDialog::OnColorOK  
 Überschreiben Sie, um die Farbe, die in das Dialogfeld eingegeben überprüfen.  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld nicht geschlossen werden soll; Andernfalls wird 0, die Farbe zu akzeptieren, die eingegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion nur, wenn Sie benutzerdefinierte Validierung der Farbe angeben, die der Benutzer im Dialogfeld Farbe auswählen möchten.  
  
 Der Benutzer kann von einem der beiden folgenden Methoden eine Farbe auswählen:  
  
-   Klicken Sie auf eine Farbe in der Farbpalette. Die ausgewählte Farbe RGB-Werte werden dann in den entsprechenden RGB-wiedergegeben.  
  
-   Eingeben von Werten in den RGB-Bearbeitungsfelder  
  
 Überschreiben von `OnColorOK` können Sie eine Farbe Ablehnen der Eingabe in ein allgemeines Dialogfeld für die Farbe von anwendungsspezifischen Gründen.  
  
 In der Regel müssen Sie nicht diese Funktion zu verwenden, da das Framework bietet eine Standard-Validierung von Farben und zeigt ein Meldungsfeld an, wenn eine ungültige Farbe eingegeben wird.  
  
 Rufen Sie [SetCurrentColor](#setcurrentcolor) aus `OnColorOK` eine Farbauswahl zu erzwingen. Einmal `OnColorOK` ausgelöst wurde (d. h. der Benutzer klickt **OK** Farbe akzeptieren), rufen Sie [GetColor](#getcolor) zum Abrufen des RGB-Wert, der die neue Farbe.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&52;](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="a-namesetcurrentcolora--ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CColorDialog::SetCurrentColor  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu erzwingen, dass die aktuelle Farbauswahl auf den Farbwert in angegebenen `clr`.  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>Parameter  
 `clr`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird in einem Message-Handler aus aufgerufen oder `OnColorOK`. Das Dialogfeld aktualisiert automatisch die Auswahl des Benutzers basierend auf den Wert der `clr` Parameter.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CColorDialog::OnColorOK](#oncolorok).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel MDI](../../visual-cpp-samples.md)   
 [MFC-Beispiel DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


