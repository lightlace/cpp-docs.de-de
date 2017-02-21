---
title: "TN043: RFX-Routinen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "RFX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RFX (Datensatzfeldaustausch)"
  - "RFX (Datensatzfeldaustausch), Architektur"
  - "TN043"
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN043: RFX-Routinen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt die Architektur des Datensatzfeldaustauschs \(RFX\).  Außerdem wird beschrieben, wie Sie eine **RFX\_** Prozedur schreiben.  
  
## Übersicht des Datensatzfeldaustauschs  
 Alle Recordsetfeldfunktionen sind mit C\+\+\-Code ausgeführt.  Es gibt keine besonderen Ressourcen oder Magic Makros.  Das Herz Mechanismus ist eine virtuelle Funktion, die in jeder abgeleiteten Recordset\-Klasse überschrieben werden muss.  Es ist stets in dieser Form gefunden:  
  
```  
void CMySet::DoFieldExchange(CFieldExchange* pFX)  
{  
  //{{AFX_FIELD_MAP(CMySet)  
  <recordset exchange field type call>  
  <recordset exchange function call>  
  //}}AFX_FIELD_MAP  
}  
```  
  
 Die speziellen Format AFX\-Kommentare ermöglichen Der Klassen\-Assistent, um den Code in dieser Funktion zu suchen und zu bearbeiten.  Code, der nicht mit die soll außerhalb der speziellen Formatkommentare platziert sind kompatibel ist.  
  
 Im obigen Beispiel \<ist recordset\_exchange\_field\_type\_call\> in der Form:  
  
```  
pFX->SetFieldType(CFieldExchange::outputColumn);  
```  
  
 und \<recordset\_exchange\_function\_call\> ist in der Form:  
  
```  
RFX_Custom(pFX, "Col2", m_Col2);  
```  
  
 Die meisten Funktionen **RFX\_** verfügen über drei Argumente wie oben dargestellt, aber einige \(z.  `RFX_Text` und `RFX_Binary`\) besitzen zusätzliche optionale Argumente.  
  
 Mehr als ein **RFX\_** möglicherweise wird in jeder `DoDataExchange`\-Funktion enthalten.  
  
 Siehe "afxdb.h" für eine Liste aller Recordsetfeld\-Austauschroutinen, die mit MFC bereitgestellt werden.  
  
 Recordsetfeldaufrufe sind eine Möglichkeit einfach von Speicheradressen \(normalerweise Datenmember\) um Felddaten für eine **CMySet**\-Klasse zu speichern.  
  
## Hinweise  
 Recordsetfeldfunktionen wurden entworfen, um nur mit `CRecordset`\-Klassen zu arbeiten.  Sie sind im Allgemeinen nicht von anderen MFC\-Klassen verwendet werden.  
  
 Anfangswerte von Daten werden in den Standard\-C\+\+\-Konstruktor, normalerweise in einem Block mit Kommentaren `//{{AFX_FIELD_INIT(CMylSet)` und `//}}AFX_FIELD_INIT` festgelegt.  
  
 Jede **RFX\_**\-Funktion muss die anderen Vorgänge unterstützen und das Zurückgeben des geänderten Status des Felds bis zum Archivieren des Felds in der Pipeline auf Bearbeiten des Felds reichen.  
  
 Jede Funktion, die `DoFieldExchange` \(zum Beispiel `SetFieldNull`, `IsFieldDirty`\) aufruft, führt seine eigene Initialisierung um den Aufruf von `DoFieldExchange`.  
  
## Funktionsweise es?  
 Sie müssen nicht, um Folgendes zu verstehen, um Datensatzfeldaustausch zu verwenden.  Jedoch hilft das Verständnis, wie dieses hinter den Kulissen bearbeitet, Ihnen, eine Prozedur der eigenen Vermittlungsstelle zu schreiben.  
  
 Die `DoFieldExchange`\-Memberfunktion ist ähnlich wie die `Serialize`\-Memberfunktion sie ist zum Abrufen oder Festlegen von Daten zur\/von der einem externen Formular \(in diesem Fall Spalten aus dem Ergebnis einer ODBC\-Abfrage\) von\/nach Memberdaten in der Klasse zuständig.  Der `pFX`\-Parameter ist der Kontext für die Variante des Datenaustausches und entspricht dem Parameter `CArchive` mit `CObject::Serialize` vergleichbar.  `pFX` \(ein `CFieldExchange`\-Objekt\) verfügt über einen Vorgangsindikator, dem zu ähnlich ist, sondern eine Verallgemeinerung des `CArchive` Richtungsflags.  Eine RFX\-Funktion muss möglicherweise die folgenden Vorgänge unterstützen:  
  
-   **BindParam** \- geben Sie an, wo die Parameterdaten abrufen soll  
  
-   **BindFieldToColumn** \- geben Sie an, wohin ODBC abrufen muss\/Einzahlung outputColumn Daten  
  
-   **Fixup** \- Set **CString\/CByteArray** Länge, UNGÜLTIGES Statusbit des Satzes  
  
-   **MarkForAddNew** \- Marke geändert, wenn der Wert als AddNew\-Aufruf geändert hat  
  
-   **MarkForUpdate** \- Marke geändert, wenn der Wert als Bearbeitungsaufruf geändert hat  
  
-   Fügen Sie **Name** \- Feldnamen für Felder markierte geändertes an  
  
-   **NameValue** \- Spalte name\=\>fügen Sie "\<?" an für Felder als geändertes  
  
-   **Wert** \- Sie fügen "?" an gefolgt vom Trennzeichen, z "," oder ''  
  
-   \-`SetFieldDirty` geänderte \(d. h geändert\) Feld von festgelegten Statusbits  
  
-   `SetFieldNull` \- Statusbit Menge, NULL\-Wert für das Feld angibt  
  
-   `IsFieldDirty` \- Rückgabewert des geänderten Statusbits  
  
-   `IsFieldNull` \- Rückgabewert des ungültigen Statusbits  
  
-   `IsFieldNullable` \- Gibt TRUE zurück, wenn das Feld NULL\-Werte enthalten kann  
  
-   **StoreField** \- Archivfeldwert  
  
-   **LoadField** \- erneute Laden archivierter Feldwert  
  
-   **GetFieldInfoValue** \- Gibt allgemeine Informationen über ein Feld zurück  
  
-   **GetFieldInfoOrdinal** \- Gibt allgemeine Informationen über ein Feld zurück  
  
## Benutzer\-Erweiterungen  
 Es gibt mehrere Möglichkeiten, den Mechanismus des Standardanbieters RFX zu erweitern.  Können Sie  
  
-   Fügen Sie neue Datentypen hinzu.  Beispiel:  
  
    ```  
    CBookmark  
    ```  
  
-   Fügen Sie neue Austauschprozeduren hinzu \(RFX\_???\).  
  
    ```  
    void AFXAPI RFX_Bigint(CFieldExchange* pFX, const char *szName,  
        BIGINT& value);  
    ```  
  
-   Haben Sie die zusätzlichen RFX `DoFieldExchange`\-Memberfunktion bedingt Aufrufe des gehören oder alle anderen C\+\+\-Anweisungen gültigen.  
  
    ```  
    while (posExtraFields != NULL)  
    {  
        RFX_Text(pFX, m_listName.GetNext(posExtraFields),   
            m_listValue.GetNext(posExtraValues));  
    }  
    ```  
  
> [!NOTE]
>  Solcher Code kann nicht durch die bearbeitet und sollte nur außerhalb der speziellen Formatkommentare verwendet werden.  
  
## Schreiben einer benutzerdefinierten RFX  
 Um eine eigene benutzerdefinierte RFX\-Funktion zu schreiben, wird es vorgeschlagen dass Sie eine vorhandene RFX\-Funktion kopieren und in eigene Zwecke ändern.  Durch Auswahl des man RFX zu kopieren kann den Auftrag viel einfacher.  Einige RFX\-Funktionen haben mehrere eindeutige Merkmale, die Sie beim Festlegen beachten sollten, das Kopieren.  
  
 **RFX\_Long und RFX\_Int**:  
 Diese sind die RFX\-Funktionen einfachsten.  Der Datenwert ist keine besondere Interpretation, und die Datengröße behoben ist.  
  
 **RFX\_Single und RFX\_Double**:  
 Wie RFX\_Long und RFX\_Int oben, sind diese Funktionen einfach und können die Standardimplementierung extensiv ausnutzen.  Sie werden in dbflt.cpp anstelle dbrfx.cpp jedoch gespeichert um das Laden der Ablaufgleitkommabibliothek zu aktivieren, wenn sie explizit Verweis sind.  
  
 **RFX\_Text und RFX\_Binary**:  
 Diese beiden Features teilen einen statischen Puffergröße, um Zeichenfolge\-\/binäre Informationen gespeichert werden und müssen diese Puffer mit ODBC SQLBindCol registrieren, anstatt, Wert &zu registrieren.  Daher haben diese beiden Funktionen viele von Sonderfallcode.  
  
 `RFX_Date`:  
 ODBC gibt Datums\- und Uhrzeitinformationen normalerweise in ihrer eigenen TIMESTAMP\_STRUCT\-Datenstruktur zurück.  Diese Funktion wird dynamisch ein TIMESTAMP\_STRUCT als "Proxy" für das Senden und Empfangen von Datum\-Zeit\-Daten zu.  Verschiedene Vorgänge müssen die Datums\- und Uhrzeitinformationen zwischen das Objekt C\+\+ `CTime` und den TIMESTAMP\_STRUCT\-Proxy übertragen.  Dies erschwert diese Funktion wesentlich, ist jedoch ein gutes Beispiel, wie einen Proxy für Datenübertragung verwendet.  
  
 `RFX_LongBinary`:  
 Dies ist die einzige Klassenbibliothek RFX\-Funktion, die nicht Spaltenbindung verwendet, um Daten zu empfangen und zu senden.  Diese Funktion ignoriert den BindFieldToColumn\-Vorgang und stattdessen, während des Fixupvorgangs, Speicher zuordnet, um die Möglichkeit SQL\_LONGVARCHAR\- oder SQL\_LONGVARBINARY\-Daten enthält, dann einen SQLGetData\-Aufruf ausführt, um den Wert in den zugeordneten Speicher abzurufen.  Beim Vorbereiten, Datenwerte in der Datenquelle übergeben \(z NameValue und Vorgänge bewerten\), berechnet diese Funktion DATA\_AT\_EXEC\-Funktionalität ODBC.  Siehe [Technischer Hinweis 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) weitere Informationen zum Arbeiten mit SQL\_LONGVARBINARY und SQL\_LONGVARCHARs.  
  
 Falls Sie Ihre eigene **RFX\_**\-Funktion schreiben, können Sie häufig in der Lage, **CFieldExchange::Default** zu verwenden, um einen angegebenen Vorgang zu implementieren.  Beachten Sie die Implementierung des Standardanbieters nach dem betreffende Vorgang.  Wenn der Vorgang ausführt, würden Sie in die **RFX\_**\-Funktion schreiben, die Sie an **CFieldExchange::Default.** delegiert werden können Sie können Beispiele des Aufrufens von **CFieldExchange::Default** in dbrfx.cpp finden  
  
 Es ist wichtig, `IsFieldType` am Anfang der RFX\-Funktion aufzurufen und wird sofort zurückgegeben, wenn es FALSE zurückgibt.  Dieser Mechanismus wird Parametervorgänge von **outputColumns** vorgenommen werden und umgekehrt \(wie das Aufrufen von **BindParam** auf **outputColumn**.\)  Außerdem verfolgt die `IsFieldType` automatisch die Anzahl von **outputColumns** \(`m_nFields`\) und Parametern verfolgen \(`m_nParams`\).  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)