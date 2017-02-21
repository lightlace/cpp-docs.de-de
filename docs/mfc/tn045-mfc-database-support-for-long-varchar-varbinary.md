---
title: "TN045: MFC- und Datenbankunterst&#252;tzung f&#252;r LONGVARCHAR und LONGVARBINARY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN045"
  - "Varbinary-Datentyp"
  - "Varchar-Datentyp"
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN045: MFC- und Datenbankunterst&#252;tzung f&#252;r LONGVARCHAR und LONGVARBINARY
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird beschrieben, wie die Datentypen ODBC\- **SQL\_LONGVARCHAR** und **SQL\_LONGVARBINARY** mit den MFC\-Datenbankklassen abruft und sendet.  
  
## Übersicht über Varchar\/von varbinary\-Unterstützung langem  
 Die Datentypen ODBC\- **SQL\_LONG\_VARCHAR** und **SQL\_LONGBINARY** \(hier bezeichnet als lange Datenspalten\) können riesige Datenmengen enthalten.  Es gibt 3 Möglichkeiten, die Sie diese Daten bearbeiten können:  
  
-   Binden Sie es in `CString`\/`CByteArray`.  
  
-   Binden Sie es an `CLongBinary`.  
  
-   Binden Sie es nichts und get und senden Sie den langen Datenwert manuell, unabhängig von den Datenbankklassen.  
  
 Jede der drei Methoden hat Vor\- und Nachteile.  
  
 Lange Datenspalten werden nicht für Parameter zu einer Abfrage unterstützt.  Sie werden nur für outputColumns unterstützt.  
  
## Binden einer langen Datenspalte zu einem CString\/CByteArray  
 Vorteile:  
  
 Dieser Ansatz ist einfach zu verstehen, und Sie arbeiten mit vertrauten Klassen.  Das Framework unterstützt `CFormView` Unterstützung für `CString` mit `DDX_Text`.  Sie haben zahlreiche allgemeine Zeichenfolgen\- oder Auflistungsfunktionen mit den `CString` und `CByteArray`\-Klassen, und Sie können den Arbeitsspeicher steuern, der lokal zugeordnet ist, dass der Datenwert aufzunehmen.  Das Framework behält einer alten Kopie von Felddaten während **Bearbeiten** oder `AddNew`\-Funktionsaufrufe bei, und das Framework kann Änderungen an den Daten automatisch feststellen.  
  
> [!NOTE]
>  Da `CString` für das Arbeiten von Textdaten und `CByteArray` für das Arbeiten auf Binärdaten vorgesehen ist, wird empfohlen, die Textdaten \(**SQL\_LONGVARCHAR**\) in `CString` setzen, und behandelt die Binärdaten \(**SQL\_LONGVARBINARY**\) in `CByteArray`.  
  
 Die RFX\-Funktionen für `CString` und `CByteArray` haben ein zusätzliches Argument, das Sie die Standardgröße des reservierten Arbeitsspeicher überschreiben können, um die abgerufenen Wert der Datenspalte aufzunehmen.  Beachten Sie das nMaxLength Argument in Funktionsdeklarationen den folgenden:  
  
```  
void AFXAPI RFX_Text(CFieldExchange* pFX, const char *szName,  
    CString& value, int nMaxLength = 255, int nColumnType =  
    SQL_VARCHAR);  
  
void AFXAPI RFX_Binary(CFieldExchange* pFX, const char *szName,   
    CByteArray& value,int nMaxLength = 255);  
```  
  
 Wenn Sie eine Datenspalte lange in `CString` oder `CByteArray` abrufen, ist das Maximum zurückgegebene Datenmenge standardmäßig 255 Bytes.  Alle über diesem hinaus wird ignoriert.  In diesem Fall löst das Framework die Ausnahme **AFX\_SQL\_ERROR\_DATA\_TRUNCATED** aus.  Glücklicherweise können Sie nMaxLength auf größere Werte, nach **MAXINT** explizit erhöhen.  
  
> [!NOTE]
>  Der Wert von nMaxLength wird von MFC verwendet, um den lokalen Puffer der **SQLBindColumn**\-Funktion festzulegen.  Dies ist der lokale Puffer für die Daten und nicht tatsächlich auswirkt die Menge der Daten, die vom ODBC\-Treiber zurückgegeben werden.  `RFX_Text` und `RFX_Binary` lassen nur einen Aufruf mit **SQLFetch** die Daten von der Back\-End\-Datenbank abrufen.  Jeder ODBC\-Treiber hat andere eine Einschränkung für die Datenmenge, die es in einem einzelnen Abruf zurückgeben können.  Diese Grenze kann viel kleiner als der Wert, der in nMaxLength festgelegt wird, in diesem Fall die Ausnahme **AFX\_SQL\_ERROR\_DATA\_TRUNCATED** ausgelöst wird.  Unter diesen Umständen, wechseln Sie zur Anwendung von `RFX_LongBinary` anstelle von `RFX_Text` oder `RFX_Binary`, um alle Daten abgerufen werden können.  
  
 Der Klassen\-Assistent bindet **SQL\_LONGVARCHAR** an `CString` oder **SQL\_LONGVARBINARY** auf `CByteArray` für Sie.  Wenn Sie mehr als 255 Bytes zuordnen möchten, in die Sie die Datenspalte lange erhalten, können Sie einen expliziten Wert für nMaxLength dann bereitstellen.  
  
 Wenn eine Datenspalte lange an `CString` oder `CByteArray` gebunden ist und die praktische Arbeiten nur die identisch aktualisiert, wenn es auf einem SQL\_**VARCHAR** oder zu SQL\_**VARBINARY** gebunden wird.  Während **Bearbeiten** wird der Datenwert weg zwischengespeichert und verglichen später, wenn **Aktualisieren** aufgerufen wird, um Änderungen am Datenwert zu erkennen und das geänderte und die NULL\-Werte für die Spalte geeignet festzulegen.  
  
## Binden einer langen Datenspalte zu einem CLongBinary  
 Wenn die Datenspalte lange **MAXINT** möglicherweise mehr Bytes Daten enthält, sollten Sie sie in `CLongBinary` abzurufen, wahrscheinlich sollten.  
  
 Vorteile:  
  
 Dies ruft eine gesamte lange Datenspalte, wenn der verfügbare Speicher ab.  
  
 Nachteile:  
  
 Die Daten werden im Arbeitsspeicher gespeichert.  Dieser Ansatz ist auch sehr große Datenmengen kostspielig aufwändig.  Sie müssen `SetFieldDirty` aufrufen, damit der Member der gebundenen Daten sicherzustellen, dass das Feld in einem Vorgang **Aktualisieren** enthalten ist.  
  
 Wenn Sie lange Datenspalten in `CLongBinary` erhalten, prüfen die Datenbankklassen die Gesamtgröße der langen Datenspalte, dann wird einem `HGLOBAL` Arbeitsspeichersegment zu, das genug, um sie aufzunehmen der gesamte Datenwert groß ist.  Die Datenbankklassen rufen den gesamten Datenwert in zugeordnete `HGLOBAL` ab.  
  
 Wenn die Datenquelle der erwarteten Größe der langen Datenspalte nicht zurückgeben kann, löst das Framework die Ausnahme **AFX\_SQL\_ERROR\_SQL\_NO\_TOTAL** aus.  Wenn der Versuch, `HGLOBAL` zuzuordnen fehlschlägt, wird eine Standardarbeitsspeicherausnahme ausgelöst.  
  
 Der Klassen\-Assistent bindet **SQL\_LONGVARCHAR** oder **SQL\_LONGVARBINARY** in `CLongBinary` für Sie.  Ausgewähltes `CLongBinary` als der Variablentyp im Hinzufügens\-Membervariablendialogfeld.  Der Klassen\-Assistent fügt dann ein `RFX_LongBinary` im Aufruf `DoFieldExchange` Aufruf hinzu und inkrementiert die Gesamtzahl von gebundenen Feldern.  
  
 Um lange Datenspaltenwerte zu aktualisieren, stellen Sie zuerst sicher dass zugeordnete `HGLOBAL` groß genug ist die neuen Daten enthalten indem es **::GlobalSize** auf dem `m_hData`\-Member `CLongBinary` aufruft.  Wenn die zu klein ist, geben Sie `HGLOBAL` freigegeben und Sie ordnen einem die entsprechende Größe zu.  Anschließend legen `m_dwDataLength`, um der neuen Größe wiederzugeben.  
  
 Wenn `m_dwDataLength` größer als die Größe der Daten, die Sie ersetzen, können Sie entweder `HGLOBAL` verwenden und neu zuordnen, oder lassen Sie es zugeordnet.  Stellen Sie sicher, der Anzahl Bytes anzugeben, die eigentlich in `m_dwDataLength` verwendet werden.  
  
## Wie Aktualisieren von einem CLongBinary funktioniert  
 Es ist nicht erforderlich, wie die Aktualisierung von `CLongBinary` zu verstehen, funktioniert, aber ggf. als Beispiel sinnvoll auf, wie lange Datenwerte zu einer Datenquelle, wenn Sie die dritte Methode auswählen, unten beschrieben sendet.  
  
> [!NOTE]
>  Damit ein `CLongBinary` Feld in einem Update eingeschlossen werden kann, müssen Sie `SetFieldDirty` für das Feld explizit aufrufen.  Wenn Sie eine Änderung an einem Feld vornehmen, einschließlich das Festlegen nicht zulässig, müssen Sie `SetFieldDirty` aufrufen.  Sie müssen `SetFieldNull` aufrufen, wenn der zweite Parameter **FALSE**, um das Feld als, einen Wert aufweist zu markieren.  
  
 Wenn ein Feld `CLongBinary`, des Datenbankklassenverwendung ODBC\- **DATA\_AT\_EXEC** der Weise aktualisiert wird \(siehe ODBC\-Dokumentation auf **SQLSetPos** rgbValue Argument\).  Wenn das Framework die INSERT\- oder UPDATE\-Anweisung vorbereitet, anstatt, auf `HGLOBAL` selbst zu zeigen, das enthält, werden die Daten, die *Funktionsadresse*`CLongBinary` als *Wert* der Spalte stattdessen und der Längenindikator, der auf **SQL\_DATA\_AT\_EXEC** festgelegt wird festgelegt.  Später wenn die Update\-Anweisung an die Datenquelle gesendet wird, gibt **SQLExecDirectSQL\_NEED\_DATA** zurück.  So werden das Framework, dass der Wert des Parameters für diese Spalte tatsächlich die Adresse von `CLongBinary`.  Das Framework ruft **SQLGetData** einmal mit einem kleinen Puffer auf und erwartet den Treiber, die tatsächliche Länge der Daten zurückzugeben.  Falls der Treiber die tatsächliche Länge des Binary Large Objects \(das BLOB\) zurückgibt, ordnet MFC so viel Platz nach Bedarf wieder, um das BLOB abzurufen.  Wenn die Datenquelle **SQL\_NO\_TOTAL** zurückgibt, der angibt, dass die Größe des BLOBS nicht bestimmen kann, MFC erstellt kleinere Blöcke.  Die Standardausgangsgröße ist im, und folgende Blöcke double sind die Größe; beispielsweise sind das 128K zweite, dritte ist 256K, u. a.  Die Ausgangsgröße ist konfigurierbar.  
  
## Nicht bei: Abrufen\/Daten das direkt von ODBC mit SQLGetData  
 Mit dieser Methode umgehen Sie vollständig die Datenbankklassen und Daten in der langen Datenspalte angezeigt.  
  
 Vorteile:  
  
 Sie können Daten auf dem Datenträger ggf. zwischenspeichern, oder entscheiden Sie dynamisch, wie viele Daten abzurufen.  
  
 Nachteile:  
  
 Rufen Sie nicht die **Bearbeiten** oder `AddNew` Unterstützung des Frameworks abgerufen, und Sie müssen Code selbst schreiben, um grundlegende Funktionen auszuführen \(**Löschen** funktioniert zwar, da kein Spaltenebenenvorgang ist\).  
  
 In diesem Fall muss die lange Datenspalte in der Select\-Liste des Recordsets werden, sollte jedoch nicht mit dem Framework gebunden werden.  Eine Möglichkeit, dies zu erreichen, eine eigene SQL\-Anweisung zu `GetDefaultSQL` oder als das lpszSQL Argument an Funktion `CRecordset`**Öffnen** zu stellen, und die zusätzliche Spalte mit einem RFX\_\-Funktionsaufruf nicht zu binden.  ODBC erfordert, dass ungebundene Felder auf der rechten Seite der gebundenen Felder werden, sodass hinzufügt ungebundenen Spalten der Spalte oder dem Ende der Auswahlliste.  
  
> [!NOTE]
>  Da die lange Datenspalte nicht vom Framework gebunden wird, werden Änderungen an ihm nicht mit Aufrufen `CRecordset::Update` behandelt.  Sie müssen SQL das erforderliche **INSERT** und **UPDATE** create\-Anweisungen und senden einander.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)