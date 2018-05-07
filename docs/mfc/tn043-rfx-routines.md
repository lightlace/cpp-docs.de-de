---
title: 'TN043: RFX-Routinen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6a46867edc4ea2f314c167da4215b869af3ab17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tn043-rfx-routines"></a>TN043: RFX-Routinen
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Datensatzfeldaustausch-Datensatzfeldaustausch (RFX)-Architektur. Es wird auch beschrieben, wie Sie schreiben eine **RFX_** Prozedur.  
  
## <a name="overview-of-record-field-exchange"></a>Übersicht über die Datensatzfeldaustausch  
 Alle Funktionen der Recordset-Feld werden mit C++-Code ausgeführt. Es gibt keine spezielle Ressourcen oder Magic-Makros. Das Herzstück des Mechanismus ist eine virtuelle Funktion, die in jeder abgeleiteten Recordsetklasse überschrieben werden muss. Es befindet sich immer oben im Formular:  
  
```  
void CMySet::DoFieldExchange(CFieldExchange* pFX)  
{ *//{{AFX_FIELD_MAP(CMySet)  
 <recordset exchange field type call>  
 <recordset exchange function call> *//}}AFX_FIELD_MAP  
}  
```  
  
 Die spezielle Format AFX Kommentare zulassen ClassWizard suchen und bearbeiten Sie den Code in dieser Funktion. Code, der nicht mit ClassWizard kompatibel ist, sollten außerhalb der besonderen Format Kommentare gespeichert werden.  
  
 Im obigen Beispiel < Recordset_exchange_field_type_call > hat das Format:  
  
```  
pFX->SetFieldType(CFieldExchange::outputColumn);
```  
  
 und < Recordset_exchange_function_call > ist in der Form:  
  
```  
RFX_Custom(pFX, "Col2",
    m_Col2);
```  
  
 Die meisten **RFX_** Funktionen haben drei Argumente wie oben dargestellt, aber einige (z. B. `RFX_Text` und `RFX_Binary`) haben Sie zusätzliche optionale Argumente.  
  
 Mehrere **RFX_** enthalten sein kann, in den einzelnen `DoDataExchange` Funktion.  
  
 Finden Sie unter "afxdb.h" eine Liste aller Recordset Feld Exchange Routinen mit MFC bereitgestellt.  
  
 Recordset-Feld-Aufrufe sind eine Möglichkeit der Registrierung für Speicherbereiche (normalerweise die Datenmember) zum Speichern von Feld-Daten für eine **CMySet** Klasse.  
  
## <a name="notes"></a>Hinweise  
 Recordset Feld Funktionen dienen nur zur Verwendung der `CRecordset` Klassen. Sie sind nicht in der Regel von anderen MFC-Klassen verwendet werden kann.  
  
 Anfangswerte Datenmengen werden festgelegt, in der standardmäßigen C++-Konstruktor in der Regel in einem Block mit `//{{AFX_FIELD_INIT(CMylSet)` und `//}}AFX_FIELD_INIT` Kommentare.  
  
 Jede **RFX_** Funktion muss unterstützen verschiedene Vorgänge, die zwischen den geänderten Status des Felds für die Archivierung des Felds als Vorbereitung für das Feld bearbeiten zurückgeben.  
  
 Jede Funktion, die Aufrufe `DoFieldExchange` (z. B. `SetFieldNull`, `IsFieldDirty`), wird eine eigene Initialisierung rund um den Aufruf `DoFieldExchange`.  
  
## <a name="how-does-it-work"></a>Wie funktioniert es  
 Sie müssen sich nicht um Folgendes zu Datensatzfeldaustausch verwenden. Jedoch verstehen, wie dies im Hintergrund funktioniert. Sie können eine eigene Exchange-Prozedur schreiben.  
  
 Die `DoFieldExchange` Memberfunktion ähnelt in vielerlei Hinsicht der `Serialize` Memberfunktion – dient zum Abrufen oder Festlegen von Daten zu/von einem externen Formular (in diesen Spalten auf Fallebene aus dem Ergebnis einer ODBC-Abfrage) vom bzw. auf Memberdaten in der Klasse. Die `pFX` Parameter ist der Kontext dafür Datenaustausch und ähnelt der `CArchive` Parameter `CObject::Serialize`. Die `pFX` (eine `CFieldExchange` Objekt) hat einen Vorgang-Indikator, der ähnlich ist, aber eine Generalisierung des der `CArchive` Richtungsflag. RFX-Funktion möglicherweise die folgenden Vorgänge zu unterstützen:  
  
- **BindParam** – Geben Sie an, in denen sollten ODBC Parameterdaten abrufen,  
  
- **BindFieldToColumn** – Geben Sie an, in dem ODBC muss abrufen/Einzahlung OutputColumn Daten,  
  
- **Fixup** – legen Sie **CString/CByteArray** Länge und NULL-Status, die bit festlegen  
  
- **MarkForAddNew** – markieren geändert, wenn der Wert geändert wurde, da AddNew aufrufen  
  
- **MarkForUpdate** – markieren modifizierte, wenn der Wert geändert wurde, da bearbeiten aufrufen  
  
- **Namen** – anfügen Feldnamen für Felder, die als geändert gekennzeichnet wurden  
  
- **NameValue** – anfügen "\<Spaltenname > =" für Felder, die als geändert gekennzeichnet wurden  
  
- **Wert** – anfügen "" gefolgt von Trennzeichen, z. B. ',' oder ' "  
  
- `SetFieldDirty` – Legen Sie die modifizierte (d. h. geänderten) Bitfeld von status  
  
- `SetFieldNull` – Legen Sie die Statusbit, der angibt, der null-Wert für Feld  
  
- `IsFieldDirty` – Rückgabewert des geänderten Status Bits  
  
- `IsFieldNull` – Rückgabewert von null-Status-bit  
  
- `IsFieldNullable` – "True" zurück, wenn das Feld NULL-Werte enthalten kann  
  
- **StoreField** – archivieren Feldwert  
  
- **LoadField** – Reload archiviert Feldwert  
  
- **GetFieldInfoValue** – allgemeine Rückgabeinformationen auf ein Feld  
  
- **GetFieldInfoOrdinal** – allgemeine Rückgabeinformationen auf ein Feld  
  
## <a name="user-extensions"></a>Benutzer-Erweiterungen  
 Es gibt mehrere Möglichkeiten zum Erweitern des standardmäßige RFX-Mechanismus. Sie haben folgende Möglichkeiten:  
  
-   Fügen Sie neue Datentypen hinzu. Zum Beispiel:  
  
 ```  
    CBookmark 
 ```  
  
-   Fügen Sie neue Exchange-Prozeduren (RFX_) hinzu.  
  
 ```  
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
    const char *szName,  
    BIGINT& value);

 ```  
  
-   Haben die `DoFieldExchange` Memberfunktion bedingt einfügen, zusätzliche RFX-Funktionsaufrufe oder eine beliebige andere gültigen C++-Anweisungen.  
  
 ```  
    while (posExtraFields != NULL)  
 {  
    RFX_Text(pFX,
    m_listName.GetNext(posExtraFields),   
    m_listValue.GetNext(posExtraValues));

 }  
 ```  
  
> [!NOTE]
>  Solcher Code kann nicht von ClassWizard nicht bearbeitet werden und sollte nur außerhalb der besonderen Format Kommentare verwendet werden.  
  
## <a name="writing-a-custom-rfx"></a>Schreiben einer benutzerdefinierten RFX  
 Um Ihre eigene benutzerdefinierte RFX-Funktion zu schreiben, wird empfohlen, dass Sie kopieren eine vorhandene RFX-Funktion und ihn für Ihre eigenen Zwecke ändern. Auswählen der richtigen RFX kopieren kann Ihr Auftrag deutlich vereinfacht. Einige RFX-Funktionen haben einige eindeutige Eigenschaften, die Sie berücksichtigen sollten bei der Entscheidung, das kopiert werden.  
  
 **RFX und RFX_Int**:  
 Hierbei handelt es sich um das einfachsten RFX-Funktionen. Der Datenwert ist es nicht erforderlich alle speziellen Interpretation ist, und die Größe der Daten.  
  
 **RFX_Single und RFX_Double**:  
 Wie RFX und RFX_Int oben, diese Funktionen sind einfach und kann die standardmäßige Implementierung umfassend nutzen. Sie werden im dbflt.cpp statt dbrfx.cpp, allerdings gespeichert um aktivieren Sie das Laden der Laufzeit floating Point-Bibliothek nur, wenn sie explizit Verweis sind.  
  
 **RFX_Text und RFX_Binary**:  
 Diese beiden Funktionen einen statischen Puffer zum Speichern der Zeichenfolge/binären Informationen vorab zugewiesen werden soll, und müssen diese Puffer mit ODBC SQLBindCol registrieren, statt registrieren & Wert. Aus diesem Grund haben diese zwei Funktionen speziellen Code für viele.  
  
 `RFX_Date`:  
 ODBC gibt Datums-und Uhrzeitinformationen in ihre eigenen TIMESTAMP_STRUCT-Datenstruktur zurück. Diese Funktion weist eine TIMESTAMP_STRUCT dynamisch als "Proxy" zum Senden und Empfangen von Uhrzeitdaten Datum. Verschiedene Vorgänge müssen Informationen Datum und Uhrzeit zwischen dem C++ übertragen `CTime` Objekt und der Proxy TIMESTAMP_STRUCT. Dies macht diese Funktion erheblich, aber es ist ein gutes Beispiel dafür, wie einen Proxy für die Datenübertragung verwendet.  
  
 `RFX_LongBinary`:  
 Dies ist die einzige Klassenbibliothek RFX-Funktion, die nicht von spaltenbindung mithilfe empfangen und Senden von Daten. Diese Funktion ignoriert den BindFieldToColumn Vorgang stattdessen während des Vorgangs Fixup reserviert Speicher, um die eingehenden SQL_LONGVARCHAR oder SQL_LONGVARBINARY Daten aufzunehmen, und führt einen SQLGetData-Aufruf zum Abrufen des Werts in den belegten Speicher. Bei der Vorbereitung zum Senden von Datenwerten mit der Datenquelle (z. B. NameValue und Wert) zurück, verwendet diese Funktion ODBCs-DATA_AT_EXEC-Funktionalität. Finden Sie unter [technischen Hinweis 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) für Weitere Informationen zum Arbeiten mit SQL_LONGVARBINARY und SQL_LONGVARCHARs.  
  
 Wenn Sie eine eigene schreiben **RFX_** -Funktion, Sie sind häufig Lage verwenden **CFieldExchange::Default** auf einen bestimmten Vorgang zu implementieren. Betrachten Sie die Implementierung der Standardwert für den entsprechenden Vorgang aus. Wenn sie den Vorgang ausführt würden Sie schreiben Ihrer **RFX_** Funktion können Sie zum Delegieren der **CFieldExchange::Default.** Sie finden Beispiele zur aufrufenden **CFieldExchange::Default** in dbrfx.cpp  
  
 Es ist wichtig, rufen Sie `IsFieldType` am Anfang der RFX-Funktion und der Rückgabewert sofort, wenn "false" zurückgegeben. Dieser Mechanismus speichert Parameter Vorgänge durchgeführt werden, auf **OutputColumns**, und umgekehrt (wie das Aufrufen **BindParam** auf eine **OutputColumn**). Darüber hinaus `IsFieldType` automatisch behält den Überblick über der Anzahl der **OutputColumns** (`m_nFields`) und Params (`m_nParams`).  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

