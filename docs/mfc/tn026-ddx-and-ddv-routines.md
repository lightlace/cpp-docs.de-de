---
title: 'TN026: DDX- und DDV-Routinen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DDX
- DDV
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f07ab7b4420a5c33be56a9278b60afb6424e9e83
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063548"
---
# <a name="tn026-ddx-and-ddv-routines"></a>TN026: DDX- und DDV-Routinen

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt den Dialogdatenaustausch (DDX) und das Dialogfeld, Data Validation, (DDV)-Architektur. Es wird beschrieben, wie Sie eine Prozedur DDX_ oder DDV_ schreiben und wie Sie die Klassen-Assistenten, um Ihre Routinen verwenden erweitern können ist.

## <a name="overview-of-dialog-data-exchange"></a>Übersicht über die Dialogfeld-Datenaustausch

Alle Funktionen der Dialogfeld-Daten werden mit C++-Code ausgeführt. Es gibt keine spezielle Ressourcen oder dem Magic-Makros. Das Herzstück des Mechanismus ist eine virtuelle Funktion, die in jedem Dialogfeldklasse außer Kraft gesetzt wird, dass Dialogdatenaustausch ist und die Überprüfung. Es befindet sich immer in dieser Form:

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

Die speziellen Format AFX Kommentare können Klassen-Assistenten, um zu suchen und bearbeiten Sie den Code in dieser Funktion. Code, der mit dem Klassen-Assistent nicht kompatibel ist, sollte außerhalb der speziellen Format Kommentare platziert werden.

Im obigen Beispiel \<Data_exchange_function_call > hat das Format:

```cpp
DDX_Custom(pDX, nIDC, field);
```

und \<Data_validation_function_call > ist optional und wird in der Form:

```cpp
DDV_Custom(pDX, field, ...);
```

Mehr als ein Paar von DDX_/DDV_ kann enthalten sein, in den einzelnen `DoDataExchange` Funktion.

Eine Liste aller dialogdatenaustauschroutinen und Validierung der Dialogfelddaten bereitgestellt, die mit MFC finden Sie unter "afxdd_.h".

Dialogfelddaten handelt es sich um: Elementdaten in die `CMyDialog` Klasse. Es ist nicht in einer Struktur oder ähnliches gespeichert.

## <a name="notes"></a>Hinweise

Obwohl wir diese Dialogfelddaten"" aufrufen, stehen alle Funktionen in jeder Klasse abgeleitet `CWnd` und sind nicht auf nur Dialogfelder beschränkt.

Die Anfangswerte der Daten werden in der standardmäßigen C++-Konstruktor, in der Regel in einem Block mit festgelegt `//{{AFX_DATA_INIT` und `//}}AFX_DATA_INIT` Kommentare.

`CWnd::UpdateData` ist der Vorgang, der die Initialisierung und rund um den Aufruf für die Fehlerbehandlung ist `DoDataExchange`.

Rufen Sie `CWnd::UpdateData` zu einem beliebigen Zeitpunkt Daten Dialogdatenaustausch und-Validierung ausführen. Standardmäßig `UpdateData`(TRUE) wird aufgerufen, in der standardmäßigen `CDialog::OnOK` Handler und `UpdateData`(FALSE) wird aufgerufen, in der standardmäßigen `CDialog::OnInitDialog`.

Die Routine DDV_ sollten sofort die DDX_-Routine, befolgen *Feld*.

## <a name="how-does-it-work"></a>Wie funktioniert es

Sie müssen nicht den folgenden Konzepten vertraut sein, um Daten für das Dialogfeld zu verwenden. Allerdings helfen zu verstehen, wie dies hinter den Kulissen funktioniert eine eigene Prozedur Exchange oder Validierung schreiben Ihnen.

Die `DoDataExchange` Memberfunktion ist ähnlich wie die `Serialize` Memberfunktion – dient zum Abrufen oder Festlegen von Daten in und aus einem externen Formular (in diesem Fall in einem Dialogfeld Steuerelemente) vom bzw. an Daten in der Klasse. Die *pDX* -Parameter ist der Kontext dafür den Datenaustausch und ähnelt der `CArchive` Parameter `CObject::Serialize`. Die *pDX* (eine `CDataExchange` Objekt) hat eine Richtung ähnelt flag `CArchive` verfügt über ein Richtungsflag:

- Wenn `!m_bSaveAndValidate`, klicken Sie dann den Zustand der Daten in die Steuerelemente zu laden.

- Wenn `m_bSaveAndValidate`, legen Sie dann den Zustand der Daten aus den Steuerelementen.

Überprüfung tritt nur auf, wenn `m_bSaveAndValidate` festgelegt ist. Der Wert des `m_bSaveAndValidate` richtet sich nach den Parameter "bool", um `CWnd::UpdateData`.

Es gibt drei andere interessante `CDataExchange` Mitglieder:

- `m_pDlgWnd`: Das Fenster (normalerweise ein Dialogfeld), das die Steuerelemente enthält. Dadurch wird verhindert, dass die Aufrufer der globalen Funktionen DDX_ und DDV_ "this" übergeben müssen jede DDX-/DDV-Routine.

- `PrepareCtrl`, und `PrepareEditCtrl`: Vorbereiten von einem Dialogfeld-Steuerelement für den Datenaustausch. Speichert dieses Steuerelements Handle zum Festlegen des Fokus, wenn es sich bei einem Überprüfungsfehler fehlschlägt. `PrepareCtrl` wird verwendet, für nicht-Edit-Steuerelemente und `PrepareEditCtrl` wird für Bearbeitungssteuerelemente verwendet.

- `Fail`: Wird aufgerufen, nachdem ein Meldungsfeld, das warnen der Benutzer die Eingabe Fehler aufzurufen. Diese Routine wird den Fokus auf das letzte Steuerelement wiederhergestellt (dem letzten Aufruf von `PrepareCtrl` oder `PrepareEditCtrl`) und löst eine Ausnahme. Diese Memberfunktion kann von sowohl DDX_ und DDV_ Routinen aufgerufen werden.

## <a name="user-extensions"></a>Benutzer-Erweiterungen

Es gibt verschiedene Möglichkeiten zum Erweitern des standardmäßige DDX-/DDV-Mechanismus. Sie haben folgende Möglichkeiten:

- Fügen Sie neue Datentypen hinzu.

    ```cpp
    CTime
    ```

- Fügen Sie die neue Exchange-Prozeduren (DDX_) hinzu.

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- Fügen Sie neue Validierungsverfahren (DDV_) hinzu.

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- Übergeben Sie beliebige Ausdrücke an die Validierungsverfahren an.

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > Solche willkürlicher Ausdrücke können nicht von Datensatzfeldern von ClassWizard nicht bearbeitet werden und daher außerhalb der speziellen Format Kommentare verschoben werden soll (/ / {{AFX_DATA_MAP(CMyClass)).

Haben die `DoDialogExchange` Member-Funktion enthalten, Bedingungen oder alle anderen gültigen C++-Anweisungen bei vermischten Dialogdatenaustausch und-Validierung-Funktionsaufrufen.

```cpp
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
> Wie oben gezeigt, wird dieser Code kann nicht von Datensatzfeldern von ClassWizard nicht bearbeitet werden und sollte nur außerhalb der speziellen Format Kommentare verwendet werden.

## <a name="classwizard-support"></a>Klassen-Assistent-Unterstützung

Klassen-Assistent unterstützt eine Teilmenge der DDX-/DDV-Anpassungen und ermöglicht Ihnen, Ihre eigenen DDX_ und DDV_ Routinen in der Klassen-Assistenten-Benutzeroberfläche integrieren. Dies ist nur Kosten von Vorteil, wenn Sie bestimmte-DDX- und DDV-Routinen in einem Projekt oder in vielen Projekten wiederverwenden möchten.

Zu diesem Zweck werden spezielle Einträge in DDX vorgenommen. CLW (frühere Versionen von Visual C++ diese Informationen in APSTUDIO gespeichert. INI) oder in Ihrem Projekts ab. CLW-Datei. Die spezielle Einträge möglich eingegeben haben, entweder im Abschnitt [allgemeine Info] Ihres Projekts. CLW-Datei oder im Abschnitt [ExtraDDX] die DDX. CLW-Datei im Verzeichnis \Programme\Microsoft Visual Studio\Visual C ++ \bin. Möglicherweise müssen Sie den DDX zu erstellen. CLW-Datei, wenn er nicht bereits vorhanden. Wenn Sie die benutzerdefinierte DDX_/DDV_-Routinen nur in einem bestimmten Projekt verwenden möchten, fügen Sie die Einträge im Abschnitt [allgemeine Info] Ihres Projekts. Die Datei stattdessen CLW. Wenn Sie die Routinen für viele Projekte verwenden möchten, fügen Sie die Einträge im Abschnitt [ExtraDDX] der DDX. CLW.

Das allgemeine Format für diese spezielle Einträge ist:

> ExtraDDXCount =*n*

wo *n* ist die Anzahl der ExtraDDX? Zeilen, die folgen, des Formulars

> ExtraDDX? =*Schlüssel*; *Vb-Schlüssel*; *Eingabeaufforderung*; *Typ*; *Startwertes*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

in welchen Bereichen? ist die Zahl 1 – *n* , der angibt, welche DDX-Typs in der Liste aus, der definiert wird.

Jedes Feld wird durch ein Zeichen ";" getrennt. Die Felder und deren Zweck werden nachfolgend beschrieben.

- *keys*

  Eine Liste der einzelnen Zeichen, der angibt, für die Dialogfeld-Steuerelemente dieser Variablentyp zulässig ist.

  |Zeichen|Zulässige-Steuerelement|
  |-|-|
  E | bearbeiten
  C | Aktivieren Sie das Kontrollkästchen zwei-Status
  c | Aktivieren Sie das Kontrollkästchen Zuständen
  R | erste Optionsfeld einer Gruppe
  L | unsortierte Listenfeld
  c | SortedList-Feld
  M | Kombinationsfeld (bei bearbeiten-Element)
  N | unsortierte Dropdownliste
  n | sortierte Dropdownliste
  1 | Wenn die Einfügung DDX auf den Anfang der Liste hinzugefügt werden sollen (Standardwert ist zu Ende hinzufügen) in der Regel dient zum DDX-Routinen, die die Eigenschaft 'Control' übertragen.

- *VB-Schlüssel*

  Dieses Feld wird nur in den 16-Bit-Produkt für VBX-Steuerelementen verwendet (VBX-Steuerelementen sind im 32-Bit-Produkt nicht unterstützt.)

- *Aufforderung*

  Die Zeichenfolge, die im Kombinationsfeld Eigenschaft (ohne Anführungszeichen) platzieren.

- *Typ*

  Einzelne Bezeichner für den Typ, in der Headerdatei auszugeben. Im Beispiel oben mit DDX_Time würde diese CTime festgelegt werden.

- *VB-Schlüssel*

  In dieser Version nicht verwendet und sollte immer leer sein.

- *Startwertes*

  Initialwert – 0 oder leer. Wenn es leer ist, wird keine initialisierungszeile im Abschnitt //{{AFX_DATA_INIT der Implementierungsdatei geschrieben werden. Ein leerer Eintrag für C++-Objekte verwendet werden soll (z. B. `CString`, `CTime`und so weiter), die über Konstruktoren, die korrekte Initialisierung garantieren verfügen.

- *DDX_Proc*

  Einzelne Bezeichner für die DDX_-Prozedur. Die Namen der C++-Funktion muss mit "DDX_" beginnen, fügen Sie jedoch nicht "DDX_" in der \<DDX_Proc > Bezeichner. Im obigen Beispiel ist die \<DDX_Proc > Bezeichner wäre Zeit. Wenn ClassWizard schreibt den Funktionsaufruf der Implementierungsdatei in die {{AFX_DATA_MAP Abschnitt er fügt diesen Namen an DDX_, daher DDX_Time eintreffen.

- *comment*

  Der Kommentar, der im Dialogfeld für die Variable mit diesem DDX angezeigt. Platzieren Sie einen beliebigen Text sollen hier und in der Regel etwas bereitzustellen, die den Vorgang mithilfe des DDX-/DDV-Paars beschreiben.

- *DDV_Proc*

  Der DDV-Teil des Eintrags ist optional. Nicht alle DDX-Routinen haben entsprechende DDV-Routinen. Häufig ist es praktischer, die Überprüfungsphase als ein wesentlicher Bestandteil in die Übertragung eingeschlossen werden sollen. Dies ist häufig der Fall, wenn Ihre DDV-Routine keine Parameter erforderlich, da ClassWizard DDV-Routinen ohne Parameter nicht unterstützt.

- *arg*

  Einzelne Bezeichner für die DDV_-Prozedur. Die Namen der C++-Funktion muss mit "DDV_" beginnen, aber nehmen Sie nicht "DDX_" in der \<DDX_Proc > Bezeichner.

  *Arg* gefolgt von 1 oder 2 DDV-Argumente:

   - *promptN*

      Zeichenfolge, die über das Bearbeiten-Element (mit & Zugriffstaste) zu platzieren.

   - *fmtN*

      Formatzeichen für den Typ eines Arg:

      |Zeichen|Typ|
      |-|-|
      |T | int|
      |n | unsigned int|
      |D | Long Int, (d. h., long)|
      |U | Langes unsingniertes (d. h. "DWORD")|
      |f | float|
      |F | double|
      |s | Zeichenfolge|

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
