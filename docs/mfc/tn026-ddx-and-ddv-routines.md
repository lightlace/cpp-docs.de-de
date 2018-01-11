---
title: 'TN026: DDX- und DDV-Routinen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DDX
- DDV
dev_langs: C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15c2309e8080892bdca2753c1ea6128ce419862f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX- und DDV-Routinen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt den Dialogdatenaustausch (DDX) und ein Dialogfeld, Data Validation, (DDV)-Architektur. Es beschreibt auch, wie Sie eine Prozedur DDX_ oder DDV_ schreiben und wie Sie Klassen-Assistenten, um Ihre Routinen verwenden erweitern können.  
  
## <a name="overview-of-dialog-data-exchange"></a>Übersicht über die Dialogfeld-Datenaustausch  
 Alle Funktionen der Dialogfeld-Daten werden mit C++-Code ausgeführt. Es gibt keine spezielle Ressourcen oder Magic-Makros. Das Kernstück des Mechanismus ist eine virtuelle Funktion, die in jedem Dialogfeldklasse außer Kraft gesetzt wird, dass Dialogdatenaustausch verfügt und die Überprüfung. Es befindet sich immer oben im Formular:  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);
*// call base class  
 *//{{AFX_DATA_MAP(CMyDialog)  
 <data_exchange_function_call>  
 <data_validation_function_call> *//}}AFX_DATA_MAP  
}  
```  
  
 Die spezielle Format AFX Kommentare zulassen ClassWizard suchen und bearbeiten Sie den Code in dieser Funktion. Code, der nicht mit ClassWizard kompatibel ist, sollten außerhalb der besonderen Format Kommentare gespeichert werden.  
  
 Im obigen Beispiel < Data_exchange_function_call > hat das Format:  
  
```  
DDX_Custom(pDX,
    nIDC,
    field);
```  
  
 und < Data_validation_function_call > ist optional und wird in der Form:  
  
```  
DDV_Custom(pDX,
    field, ...);
```  
  
 Mehr als ein Paar von DDX_/DDV_ kann in jeder aufgenommen werden `DoDataExchange` Funktion.  
  
 Eine Liste aller dialogdatenaustauschroutinen und zur Validierung der Dialogfelddaten bereitgestellt, die mit MFC finden Sie unter "afxdd_.h".  
  
 Dialogfelddaten handelt es sich um: Elementdaten in die **CMyDialog** Klasse. Es ist nicht in einer Struktur oder ähnliches gespeichert.  
  
## <a name="notes"></a>Hinweise  
 Obwohl wir diese Dialogfelddaten"" aufrufen, stehen alle Funktionen in einer Klasse abgeleitet `CWnd` und sind nicht auf nur Dialoge beschränkt.  
  
 Anfangswerte Datenmengen werden festgelegt, in der standardmäßigen C++-Konstruktor in der Regel in einem Block mit `//{{AFX_DATA_INIT` und `//}}AFX_DATA_INIT` Kommentare.  
  
 `CWnd::UpdateData`ist der Vorgang, der die Initialisierung als auch die Fehlerbehandlung rund um den Aufruf durchführt `DoDataExchange`.  
  
 Sie können Aufrufen `CWnd::UpdateData` zu einem beliebigen Zeitpunkt zum Datenaustausch und die Validierung ausführen. Standardmäßig `UpdateData`("true") wird aufgerufen, in der standardmäßigen `CDialog::OnOK` Handler und `UpdateData`("false") wird aufgerufen, in der standardmäßigen `CDialog::OnInitDialog`.  
  
 Die Routine DDV_ befolgen sofort die Routine DDX_ für diesen *Feld*.  
  
## <a name="how-does-it-work"></a>Wie funktioniert es  
 Sie müssen sich nicht um Folgendes zu Dialogfelddaten verwenden. Allerdings hilft Grundlegendes zur Funktionsweise im Hintergrund eine eigene Prozedur Exchange oder Validierung schreiben Ihnen.  
  
 Die `DoDataExchange` Memberfunktion ähnelt in vielerlei Hinsicht der `Serialize` Memberfunktion - es dient zum Abrufen oder Festlegen von Daten zu/von einem externen Formular (in diesem Fall in einem Dialogfeld-Steuerelemente) vom bzw. auf Memberdaten in der Klasse. Die `pDX` Parameter ist der Kontext dafür Datenaustausch und ähnelt der `CArchive` Parameter `CObject::Serialize`. Die `pDX` (eine `CDataExchange` Objekt) verfügt über eine Richtung viele ähnliche flag `CArchive` verfügt über ein Kennzeichen Richtung:  
  
-   Wenn **! M_bSaveAndValidate**, laden Sie den Datenzustand in die Steuerelemente.  
  
-   Wenn `m_bSaveAndValidate`, legen Sie den Datenzustand aus den Steuerelementen.  
  
 Überprüfung erfolgt nur, wenn `m_bSaveAndValidate` festgelegt ist. Der Wert der `m_bSaveAndValidate` richtet sich nach dem BOOL-Parameter `CWnd::UpdateData`.  
  
 Es gibt drei weitere interessante `CDataExchange` Elemente:  
  
- `m_pDlgWnd`: Das Fenster (normalerweise ein Dialogfeld "), das die Steuerelemente enthält. Dadurch wird verhindert, dass Aufrufer DDX_ und DDV_ globalen Funktionen "this" übergeben müssen jede DDX-/DDV-Routine.  
  
- `PrepareCtrl`, und `PrepareEditCtrl`: bereitet ein dialogsteuerelement für den Datenaustausch. Speichert dieses Steuerelement Handle zum Festlegen des Fokus, wenn es sich bei einem Überprüfungsfehler fehlschlägt. `PrepareCtrl`wird für Steuerelemente Nonedit verwendet und `PrepareEditCtrl` für Bearbeitungssteuerelemente verwendet wird.  
  
- **Fehler**: aufgerufen, nachdem ein Meldungsfeld mit den Benutzer die Eingabefehler Warnungen zu schalten. Diese Routine wird den Fokus auf das letzte Steuerelement wiederherstellen (dem letzten Aufruf von `PrepareCtrl` / `PrepareEditCtrl`) und löst eine Ausnahme. Diese Memberfunktion kann von DDX_ und DDV_ Routinen aufgerufen werden.  
  
## <a name="user-extensions"></a>Benutzer-Erweiterungen  
 Es gibt mehrere Möglichkeiten zum Erweitern des standardmäßige DDX-/DDV-Mechanismus. Sie haben folgende Möglichkeiten:  
  
-   Fügen Sie neue Datentypen hinzu.  
  
 ```  
    CTime 
 ```  
  
-   Fügen Sie neue Exchange-Prozeduren (DDX_) hinzu.  
  
 ```  
    void PASCAL DDX_Time(CDataExchange* pDX,
    int nIDC,
    CTime& tm);

 ```  
  
-   Fügen Sie neue Validierungsverfahren (DDV_) hinzu.  
  
 ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX,
    CTime tm,
    BOOL bFuture);
*// make sure time is in the future or past  
 ```  
  
-   Übergeben Sie die Validierungsverfahren willkürlicher Ausdrücke ein.  
  
 ```  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxAge);

 ```  
  
    > [!NOTE]
    >  Solche willkürlicher Ausdrücke können nicht von ClassWizard nicht bearbeitet werden und sollte daher verschoben werden, außerhalb der besonderen Format Kommentare (/ / {{AFX_DATA_MAP(CMyClass)).  
  
 Haben die **DoDialogExchange** Memberfunktion enthalten Konditionelle Abschnitte oder allen anderen gültigen C++-Anweisungen mit gemischt Dialogdatenaustausch und-Validierung Funktionsaufrufe.  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX,
    IDC_SEX,
    m_bFemale);

DDX_Text(pDX,
    IDC_EDIT1,
    m_age);

//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxFemaleAge);

else  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxMaleAge);
```  
  
> [!NOTE]
>  Wie oben gezeigt, wird solcher Code kann nicht von ClassWizard nicht bearbeitet werden und sollte nur außerhalb der besonderen Format Kommentare verwendet werden.  
  
## <a name="classwizard-support"></a>Klassen-Assistent-Unterstützung  
 Klassen-Assistent unterstützt eine Teilmenge der DDX-/DDV-Anpassungen können Sie Ihre eigenen DDX_ und DDV_ Routinen in der Benutzeroberfläche ClassWizard zu integrieren. Dies ist nur Kosten vorteilhaft, wenn Sie bestimmte-DDX- und DDV-Routinen in einem Projekt oder in zahlreiche Projekte wiederverwenden möchten.  
  
 Zu diesem Zweck werden spezielle Einträge in DDX vorgenommen. CLW (frühere Versionen von Visual C++ diese Informationen in APSTUDIO gespeichert. INI) oder in Ihrem Projekts. CLW-Datei. Die spezielle Einträge kann entweder im Abschnitt [allgemeine Info] Ihres Projekts eingegeben. CLW-Datei oder im Abschnitt [ExtraDDX] der DDX. CLW-Datei im Verzeichnis \Programme\Microsoft Visual Studio\Visual C ++ \bin. Sie müssen möglicherweise die DDX zu erstellen. CLW-Datei, falls er nicht bereits vorhanden. Wenn Sie die benutzerdefinierte DDX_/DDV_-Routinen nur in einem bestimmten Projekt verwenden möchten, fügen Sie die Einträge im Abschnitt [allgemeine Info] des Projekts. Die Datei stattdessen CLW. Wenn Sie die Routinen in mehreren Projekten verwenden möchten, fügen Sie die Einträge im Abschnitt [ExtraDDX] DDX. CLW.  
  
 Das allgemeine Format dieser speziellen Einträge ist:  
  
```  
ExtraDDXCount=n  
```  
  
 wobei n die Anzahl der Zeilen von ExtraDDX anzuwendendes ist  
  
```  
ExtraDDX=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 Dabei ist eine Zahl von 1: n, der angibt, welche DDX-Typs in der Liste, die definiert wird.  
  
 Jedes Feld wird durch ein ";"-Zeichen begrenzt. Die Felder und deren Verwendungszweck werden nachfolgend beschrieben.  
  
 \<Schlüssel >  
 = die Liste der einzelnen Zeichen, der angibt, für welche Dialogfeld-Steuerelemente dieser Variablentyp zulässig ist.  
  
 E = bearbeiten  
  
 C = zwei-Status-Kontrollkästchen  
  
 c = Zuständen-Kontrollkästchen  
  
 R = erste Optionsfeld einer Gruppe  
  
 L = unsortierte Listenfeld  
  
 l = sortierten Listenfeld  
  
 M = Kombinationsfeld (durch Bearbeiten-Element)  
  
 N = unsortierte Dropdownliste  
  
 n = sortierten Dropdownliste  
  
 1 = DDX einfügen zu Anfang der Liste hinzugefügt werden soll (Standardwert ist Tail hinzufügen) in der Regel dient zum DDX-Routinen, die die Eigenschaft "Control" übertragen.  
  
 \<VB-Schlüssel >  
 Dieses Feld wird nur in der 16-Bit-Produkt für VBX Steuerelemente verwendet (VBX-Steuerelemente sind in der 32-Bit-Produkt nicht unterstützt.)  
  
 \<Eingabeaufforderung >  
 Die Zeichenfolge, die im Kombinationsfeld Eigenschaft (ohne Anführungszeichen) platzieren.  
  
 \<type>  
 Einzelnen Bezeichner für den Typ in der Headerdatei auszugeben. In unserem Beispiel oben mit DDX_Time würde diese CTime festgelegt werden.  
  
 \<VB-Schlüssel >  
 In dieser Version nicht verwendet und sollte immer leer sein.  
  
 \<Startwertes >  
 Wert der ersten – 0 oder leer. Wenn sie leer ist, wird keine Initialisierung Linie im Abschnitt //{{AFX_DATA_INIT der Implementierungsdatei geschrieben werden. Ein leerer Eintrag für C++-Objekte verwendet werden soll (z. B. `CString`, `CTime`usw.), die über Konstruktoren, die korrekte Initialisierung zu garantieren, verfügen.  
  
 < DDX_Proc >  
 Einzelne Bezeichner für die DDX_-Prozedur. Den Namen der C++-Funktion muss mit "DDX_" beginnen, aber nicht "DDX_" in der < DDX_Proc > Bezeichner enthalten. Im obigen Beispiel wäre der < DDX_Proc > Bezeichner Zeit. Wenn schreibt ClassWizard Aufruf der Funktion in der Implementierungsdatei in die {{AFX_DATA_MAP-Abschnitt, er fügt diesen Namen an DDX_, daher bei DDX_Time ankommen.  
  
 \<Kommentar >  
 Kommentar im Dialogfeld für die Variable mit diesem DDX angezeigt. Platzieren Sie einen beliebigen Text Sie hier und in der Regel etwas bereitstellen möchten, die Beschreibung des Vorgangs durch die DDX-/DDV-Paar ausgeführt.  
  
 < DDV_Proc >  
 Der DDV-Teil der Eintrag ist optional. Nicht alle DDX-Routinen haben entsprechende DDV-Routinen. Häufig ist es praktischer sein, die Überprüfungsphase als wesentlicher Bestandteil der Übertragung enthalten. Dies ist häufig der Fall, wenn Ihre DDV-Routine keine Parameter erforderlich da ClassWizard DDV-Routinen ohne Parameter nicht unterstützt.  
  
 \<Arg >  
 Einzelne Bezeichner für die DDV_-Prozedur. Die Namen der C++-Funktion muss mit "DDV_" beginnen, aber schließen Sie "DDX_" nicht in der < DDX_Proc > Bezeichner.  
  
 gefolgt von 1 oder 2 DDV-Args:  
  
 \<PromptX >  
 Zeichenfolge, die über das Element bearbeiten (mit & Accelerator) platzieren.  
  
 \<FmtX >  
 Formatzeichen für den Arg-Typ ist eine der  
  
 d = Int  
  
 u = ohne Vorzeichen  
  
 D = long Int (d. h., long)  
  
 U = lange ohne Vorzeichen (d. h. "DWORD")  
  
 f = "float"  
  
 F = double  
  
 s = Zeichenfolge  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

