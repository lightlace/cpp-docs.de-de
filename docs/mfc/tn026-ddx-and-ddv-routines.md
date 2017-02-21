---
title: "TN026: DDX- und DDV-Routinen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DDX"
  - "DDV"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DDV (Dialog Data Validation - Validieren von Dialogfelddaten), Prozeduren"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Prozeduren"
  - "TN026"
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN026: DDX- und DDV-Routinen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis Datenvalidierungs \(ddv\)\- beschreibt die Architektur des Dialogdatenaustauschs \(DDX\) und des Dialogfelds.  Er beschreibt außerdem, wie Sie eine DDX\_\- oder DDV\_\-Prozedur schreiben und wie Sie des Klassen\-Assistenten erweitern können, um die Routinen zu verwenden.  
  
## Übersicht des Dialogdatenaustauschs  
 Alle Dialogfelddatenfunktionen sind mit C\+\+\-Code ausgeführt.  Es gibt keine besonderen Ressourcen oder Magic Makros.  Das Herz Mechanismus ist eine virtuelle Funktion, die in jeder Dialogfeldklasse überschrieben wird, die den Dialogdatenaustausch und Validierung ausführt.  Es ist stets in dieser Form gefunden:  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);    // call base class  
  
    //{{AFX_DATA_MAP(CMyDialog)  
        <data_exchange_function_call>  
        <data_validation_function_call>  
    //}}AFX_DATA_MAP  
}  
```  
  
 Die speziellen Format AFX\-Kommentare ermöglichen Der Klassen\-Assistent, um den Code in dieser Funktion zu suchen und zu bearbeiten.  Code, der nicht mit die soll außerhalb der speziellen Formatkommentare platziert sind kompatibel ist.  
  
 Im obigen Beispiel \<ist data\_exchange\_function\_call\> in der Form:  
  
```  
DDX_Custom(pDX, nIDC, field);  
```  
  
 und \<data\_validation\_function\_call\> ist optional und befindet sich in der Form:  
  
```  
DDV_Custom(pDX, field, ...);  
```  
  
 Mehr als ein DDX\_\-\/DDV\_paar möglicherweise wird in jeder `DoDataExchange`\-Funktion enthalten.  
  
 Siehe "afxdd\_.h" für eine Liste aller Dialogdatenaustauschroutinen und wählen Sie die Datenvalidierungsroutinen, die mit MFC bereitgestellt werden.  
  
 Dialogfelddaten sind derzeit das: Memberdaten in der **CMyDialog**\-Klasse.  Sie wird in einer, Struktur oder nichts gespeichert.  
  
## Hinweise  
 Obwohl Sie diese "Dialogfelddaten aufrufen," sind alle Funktionen in einer Klasse verfügbar, die von `CWnd` abgeleitet wird und werden nicht in den aktuell Dialogfeldern beschränkt.  
  
 Anfangswerte von Daten werden in den Standard\-C\+\+\-Konstruktor, normalerweise in einem Block mit Kommentaren `//{{AFX_DATA_INIT` und `//}}AFX_DATA_INIT` festgelegt.  
  
 `CWnd::UpdateData` ist der Vorgang, der die Initialisierung und die Fehlerbehandlung um den Aufruf von `DoDataExchange` erreichen.  
  
 Sie können `CWnd::UpdateData` jederzeit aufrufen, um Datenaustausch und Validierung auszuführen.  `UpdateData` ist standardmäßig \(TRUE\) im Standard `CDialog::OnOK`\-Handler aufgerufen und `UpdateData` FALSE \(Standard\) wird im `CDialog::OnInitDialog` aufgerufen.  
  
 Die DDV\_\-Routine sollte der DDX\_\-Routine für dieses *Feld* sofort ausführen.  
  
## Funktionsweise es?  
 Sie müssen nicht, um Folgendes zu verstehen, um Dialogfelddaten zu verwenden.  Jedoch hilft das Verständnis, wie dieses hinter den Kulissen bearbeitet, Ihnen, eine Prozedur der eigenen Vermittlungsstelle oder der Validierung zu schreiben.  
  
 Die `DoDataExchange`\-Memberfunktion ist ähnlich wie die `Serialize`\-Memberfunktion sie ist zum Abrufen oder Festlegen von Daten zur\/von der einem externen Formular \(in diesem Fall Steuerelemente in einem Dialogfeld\/nach\) von Memberdaten in der Klasse zuständig.  Der `pDX`\-Parameter ist der Kontext für die Variante des Datenaustausches und entspricht dem Parameter `CArchive` mit `CObject::Serialize` vergleichbar.  `pDX` \(ein `CDataExchange`\-Objekt\) weist ein Richtungsflag ähnlich wie `CArchive` verfügt über ein Richtungsflag:  
  
-   Wenn **\!m\_bSaveAndValidate**, anschließend den Datenzustand in die Steuerelemente laden.  
  
-   Wenn `m_bSaveAndValidate`, dann den Datenzustand von Steuerelementen fest.  
  
 Validierung tritt nur auf, wenn `m_bSaveAndValidate` festgelegt wird.  Der Wert von `m_bSaveAndValidate` wird von der BOOL\-Parameter in `CWnd::UpdateData` bestimmt.  
  
 Es gibt drei weitere interessante `CDataExchange`\-Member:  
  
-   `m_pDlgWnd`: Das Fenster \(normalerweise ein Dialogfeld\) das die Steuerelemente enthält.  Dies ist, Aufrufer des DDX\_ und des DDV\_ zu verhindern, die globale Funktionen von der dieses übergibt" zu jeder DDX\-\/DDVroutine müssen.  
  
-   `PrepareCtrl` und `PrepareEditCtrl`: Bereitet ein Dialogfeld\-Steuerelement Datenaustausch für vor.  Speicher das dieses Handle des Steuerelements zum Festlegen des Fokus, wenn die Validierung fehlschlägt.  `PrepareCtrl` wird für nonedit Steuerelemente verwendet und `PrepareEditCtrl` wird für Bearbeitungssteuerelemente verwendet.  
  
-   **Fehler**: Wird aufgerufen, nachdem oben ein Meldungsfeld geholt wurde, dem Benutzer das Eingabefehlers werden.  Diese Routine wird der Fokus auf das letzte Steuerelement \(der letzte Aufruf von `PrepareCtrl`\/`PrepareEditCtrl`\) zurückgesetzt und löst eine Ausnahme aus.  Diese Memberfunktion wird von DDX\_\- und DDV\_\-Routinen aufgerufen werden.  
  
## Benutzer\-Erweiterungen  
 Es gibt mehrere Möglichkeiten, den Mechanismus des standardmäßigen DDX\/DDV zu erweitern.  Folgende Aktionen sind möglich:  
  
-   Fügen Sie neue Datentypen hinzu.  
  
    ```  
    CTime  
    ```  
  
-   Fügen Sie neue Austauschprozeduren hinzu \(DDX\_???\).  
  
    ```  
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);  
    ```  
  
-   Fügen Sie neue Validierungsprozeduren hinzu \(DDV\_???\).  
  
    ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);  
    // make sure time is in the future or past  
    ```  
  
-   Führen Sie beliebige Ausdrücke zu den Validierungsprozeduren.  
  
    ```  
    DDV_MinMax(pDX, age, 0, m_maxAge);  
    ```  
  
    > [!NOTE]
    >  Solche beliebigen Ausdrücke können nicht durch die bearbeitet werden sollten und außerhalb der speziellen Formatkommentare daher werden verschoben \(\/\/ {{AFX\_DATA\_MAP \(CMyClass\)\).  
  
 Haben Sie die **DoDialogExchange**\-Memberfunktionseinschließung Bedingungen oder alle anderen C\+\+\-Anweisungen mit gültigen vermischten Austausch\- und Validierungsfunktionsaufrufen.  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX, IDC_SEX, m_bFemale);  
DDX_Text(pDX, IDC_EDIT1, m_age);  
//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);  
else  
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);  
```  
  
> [!NOTE]
>  Wie oben gezeigt, kann dieser Code nicht durch die bearbeitet und sollte nur außerhalb der speziellen Formatkommentare verwendet werden.  
  
## ClassWizard\-Unterstützung  
 Der Klassen\-Assistent unterstützt eine Teilmenge DDX\-\/DDVanpassungen, indem es Ihnen ermöglicht, eigene DDX\_\- und DDV\_\-Routinen in die ClassWizard\-Benutzeroberfläche zu integrieren.  Hierdurch wird nur nützliches gemacht, wenn Sie planen, bestimmtes DDX und DDV\-Routinen in einem Projekt oder in vielen Projekten wiederzuverwenden.  
  
 Um dies zu erreichen, werden spezielle Einträge in DDX.CLW \(In früheren Versionen von Visual C\+\+ wurden diese Informationen in APSTUDIO.INI\) oder in das .CLW\-Datei des Projekts ausgeführt.  Die speziellen Einträge können entweder in den Abschnitt \[der allgemeinen Informationen\] aus das .CLW\-Datei des Projekts oder in den Abschnitt \[ExtraDDX\] der Datei DDX.CLW im Verzeichnis \\Programme\\Microsoft Visual Studio\\Visual C\+\+\\bin eingegeben werden.  Sie müssen ggf. die DDX.CLW\-Datei erstellen, wenn sie nicht bereits vorhanden ist.  Wenn Sie planen, die Routinen der benutzerdefinierten DDX\_\/DDV\_ nur in einem bestimmten Projekt zu verwenden, fügen die Einträge im Abschnitt \[der allgemeinen Informationen\] der Datei des Projekts .CLW stattdessen hinzu.  Wenn Sie planen, die Routinen zu vielen Projekten verwenden, fügen die Einträge im Abschnitt \[ExtraDDX\] von DDX.CLW hinzu.  
  
 Das Muster dieser speziellen Einträge ist:  
  
```  
ExtraDDXCount=n  
```  
  
 wobei n ist die Anzahl der ExtraDDX? Zeilen zu folgen  
  
```  
ExtraDDX?=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 wobei? entspricht einer Zahl. 1 \- n\-Angeben, DDX dem die Liste in, die definiert wird.  
  
 Jedes Feld wird durch "getrennt; " Zeichen.  Die Felder und ihr Zweck sind unten beschrieben.  
  
 \<keys\>  
 \= wird Liste aus einzelnen Zeichen, die angeben, welche Dialogfeld, für diesen Variablentyp steuert, zulässig.  
  
 E \= Bearbeiten  
  
 C \= ZweiZustandskontrollkästchen  
  
 c \= Tristatekontrollkästchen  
  
 R \= ersten Optionsfeld in einer Gruppe  
  
 L \= nonsorted Listenfeld  
  
 L \= sortiertes Listenfeld  
  
 M \= Kombinationsfeld \(mit Bearbeitungselement\)  
  
 N \= nonsorted Ablagenliste  
  
 n \= sortierte Ablagenliste  
  
 1 \=, wenn die DDX\-Einfügung hinzugefügt den Anfang der Liste \(Standard, hinzufügen Ende\), das dies üblicherweise für DDX\-Routinen verwendet wird, die die "Steuer" Eigenschaft übertragen.  
  
 \<VBTasten\>  
 Dieses Feld ist nur im 16\-Bit\-Produkt für VBX\-Kontrollen verwendet \(VBX\-Kontrollen werden nicht im 32\-Bit\-Produkt unterstützt\)  
  
 \<Eingabeaufforderung\>  
 In das Eigenschaftenkombinationsfeld \(keine Anführungszeichen\) zu legen, Zeichenfolge  
  
 \<type\>  
 Einzelner Bezeichner, sodass Typ in der Headerdatei ausgibt.  In unserem Beispiel oben mit DDX\_Time, würde dies auf CTime festgelegt.  
  
 \<VBTasten\>  
 Wird in dieser Version nicht und sollte immer leer sein  
  
 \<initValue\>  
 Anfangswert \- 0 oder Leerzeichen.  Wenn es leer, wird keine Initialisierungszeile in \/\/geschrieben {{AFX\_DATA\_INIT\-Abschnitt der Implementierungsdatei.  Ein leerer Eintrag sollte für C\+\+\-Objekte verwendet werden \(beispielsweise `CString`, `CTime` usw.\)., die über Konstruktoren verfügen, richtiger die Initialisierung sicherstellen.  
  
 \<DDX\_Proc\>  
 Einzelner Bezeichner für die DDX\_\-Prozedur.  Der C\+\+\-Funktionsname muss mit "DDX\_ starten, aber" enthält "DDX\_" nicht im \<DDX\_Proc\-Bezeichner\>.  Im Beispiel oben, wird der \<DDX\_Proc\-Bezeichner\> vorhanden sein.  Wenn Der Klassen\-Assistent den Funktionsaufruf der Implementierungsdatei schreibt in {{AFX\_DATA\_MAP\-Abschnitt, fügt dieser Namen zu DDX\_ an und so wird bei DDX\_Time an.  
  
 \<Kommentar\>  
 Kommentieren Sie, um im Dialogfeld für Variable mit diesem DDX zu veranschaulichen.  Platzieren Sie jeden Text, den Sie hier möchten, und stellen Sie normalerweise einige bereit, das beschreibt den Vorgang, der von der DDX\-\/DDVpaare ausgeführt wird.  
  
 \<DDV\_Proc\>  
 Der DDV\-Teil des Eintrags ist optional.  Nicht alle DDX\-Routinen haben das häufig von DDV\-Routinen.  Häufig ist es einfacher, die Validierungsphase als ganzzahliger Teil der Übertragung einzuschließen.  Dies ist häufig der Fall, wenn die DDV\-Routine keine Parameter benötigt, da die DDV\-Routinen nicht ohne Parameter unterstützt.  
  
 \<Argument\>  
 Einzelner Bezeichner für die DDV\_\-Prozedur.  Der C\+\+\-Funktionsname muss mit "DDV\_" starten, aber enthält "DDX\_" nicht im \<DDX\_Proc\-Bezeichner\>.  
  
 gefolgt von 1 oder 2 DDV\-args:  
  
 \<promptX\>  
 zum Bearbeitungselement zu platzieren, Zeichenfolge \(mit & für Zugriffstaste\)  
  
 \<fmtX\>  
 Formatzeichen für den Typ, der ein Argument  
  
 d \= int  
  
 & \= ohne Vorzeichen  
  
 D \= lang int \(das heißt, long\)  
  
 U \= lang ohne Vorzeichen \(das heißt, DWORD\)  
  
 f \= float  
  
 F \= Double  
  
 s \= Zeichenfolge  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)