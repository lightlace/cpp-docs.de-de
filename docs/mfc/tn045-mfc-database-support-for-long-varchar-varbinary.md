---
title: 'TN045: MFC-Datenbankunterstützung für Long Varchar-Varbinary'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.data
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
ms.openlocfilehash: d356f094759775f709838de149769b1671fdf9ba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57260113"
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: MFC-und Datenbankunterstützung für Long LONGVARBINARY

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

In diesem Hinweis wird beschrieben, wie zum Abrufen und senden die ODBC **SQL_LONGVARCHAR** und **SQL_LONGVARBINARY** Datenbank Datentypen mithilfe von MFC-Klassen.

## <a name="overview-of-long-varcharvarbinary-support"></a>Übersicht über die Unterstützung für lange LONGVARBINARY

Die ODBC **SQL_LONG_VARCHAR** und **SQL_LONGBINARY** -Datentypen (hier als lange Datenspalten bezeichnet) können große Datenmengen enthalten. Es gibt 3 Möglichkeiten, die Sie diese Daten verarbeitet werden können:

- Binden Sie es an eine `CString` / `CByteArray`.

- Binden Sie es an eine `CLongBinary`.

- Keine binden Sie es überhaupt zu und abzurufen Sie, und senden Sie den Wert des long-Daten manuell, unabhängig von den Datenbankklassen.

Jede der drei Methoden hat vor- und Nachteile.

Long-Daten-Spalten werden für die Parameter für eine Abfrage nicht unterstützt. Sie werden nur für OutputColumns unterstützt.

## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Binden eine Spalte lange Daten an eine CString/CByteArray

Vorteile:

Dieser Ansatz ist einfach zu verstehen, und arbeiten Sie mit vertrauten Klassen. Das Framework bietet `CFormView` Unterstützung für `CString` mit `DDX_Text`. Ihnen stehen viele allgemeine Funktionalität mit Zeichenfolge oder eine Auflistung mit den `CString` und `CByteArray` Klassen, und Sie können steuern, die Speichermenge, die lokal aus, um den Datenwert enthalten soll. Das Framework verwaltet eine alte Kopie der Daten während der `Edit` oder `AddNew` -Funktionsaufrufe und das Framework kann Änderungen an den Daten für Sie automatisch zu erkennen.

> [!NOTE]
>  Da `CString` dient für die Arbeit auf Zeichendaten und `CByteArray` für binäre Daten ausgeführt werden, wird empfohlen, die Zeichendaten zu speichern (**SQL_LONGVARCHAR**) in `CString`, und die binären Daten ( **SQL_LONGVARBINARY**) in `CByteArray`.

Der RFX-Funktionen für `CString` und `CByteArray` ein zusätzliches Argument haben, können Sie die Standardgröße des zugeordneten Speichers für den abgerufenen Wert für die Datenspalte außer Kraft setzen. Beachten Sie das Argument nMaxLength in den folgenden Funktionsdeklarationen:

```
void AFXAPI RFX_Text(CFieldExchange* pFX,
    const char *szName,
    CString& value,
    int nMaxLength = 255,
    int nColumnType =
    SQL_VARCHAR);

void AFXAPI RFX_Binary(CFieldExchange* pFX,
    const char *szName,
    CByteArray& value,
    int nMaxLength = 255);
```

Wenn Sie eine Spalte lange Daten in Abrufen einer `CString` oder `CByteArray`, der größte zurückgegeben Datenmenge ist, wird standardmäßig 255 Bytes. Alles darüber hinaus wird ignoriert. In diesem Fall löst das Framework die Ausnahme **AFX_SQL_ERROR_DATA_TRUNCATED**. Glücklicherweise können Sie explizit erhöhen nMaxLength auf größere Werte bis zu **MAXINT**.

> [!NOTE]
>  Der Wert der nMaxLength wird von MFC verwendet, den lokalen Puffer mit Festlegen der `SQLBindColumn` Funktion. Dies ist von der lokalen Puffer für die Speicherung der Daten und tatsächlich wirkt sich nicht die Menge der Daten, die vom ODBC-Treiber zurückgegeben. `RFX_Text` und `RFX_Binary` stellen nur einen Anruf `SQLFetch` zum Abrufen der Daten aus der Back-End-Datenbank. Jede ODBC-Treiber hat eine andere Einschränkung auf die Menge der Daten, die sie in einer einzigen Abfrage zurückgeben können. Dieser Grenzwert ist möglicherweise wesentlich kleiner als der Wert in nMaxLength, in diesem Fall die Ausnahme **AFX_SQL_ERROR_DATA_TRUNCATED** ausgelöst. Unter diesen Umständen wechseln in den `RFX_LongBinary` anstelle von `RFX_Text` oder `RFX_Binary` , damit alle Daten abgerufen werden können.

Klassen-Assistenten wird eine Bindung erstellt eine **SQL_LONGVARCHAR** auf eine `CString`, oder ein **SQL_LONGVARBINARY** auf eine `CByteArray` für Sie. Wenn Sie mehr als 255 Byte zugeordnet, in denen Sie die Spalte lange Daten abrufen, möchten, können Sie dann einen expliziten Wert für nMaxLength angeben.

Wenn eine Spalte lange Daten gebunden ist, um eine `CString` oder `CByteArray`, aktualisieren das Feld wie bei der Bindung an eine SQL_ funktioniert**VARCHAR** oder SQL_**VARBINARY**. Während der `Edit`, entfernt und später verglichen, wenn der Wert zwischengespeichert `Update` wird aufgerufen, um das Erkennen von Änderungen an den Daten Wert und legen Sie die Dirty und Null-Werte für die Spalte entsprechend.

## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Binden eine Spalte lange Daten an eine CLongBinary

Wenn die Spalte lange Daten mehr enthalten möglicherweise **MAXINT** Datenbytes, wahrscheinlich sollten Sie es in abrufen eine `CLongBinary`.

Vorteile:

Dies ruft die einer Spalte mit ganzen long-Daten, bis zu den verfügbaren Arbeitsspeicher ab.

Nachteile:

Die Daten werden im Arbeitsspeicher gespeichert. Dieser Ansatz ist auch für sehr große Mengen an Daten sehr teuer. Rufen Sie `SetFieldDirty` Member, um sicherzustellen, dass das Feld ist für die gebundenen Daten in enthalten eine `Update` Vorgang.

Wenn Abrufen von long-Daten-Spalten in einer `CLongBinary`, Datenbankklassen stellt die Gesamtgröße der Spalte lange Daten überprüfen und dann Zuordnen einer `HGLOBAL` Speichersegment groß genug für es den gesamten Datenwert. Die Datenbankklassen abrufen klicken Sie dann den gesamten Datenwert in der zugeordneten `HGLOBAL`.

Wenn die Datenquelle die erwartete Größe der Spalte lange Daten zurückgeben kann, löst das Framework die Ausnahme **AFX_SQL_ERROR_SQL_NO_TOTAL**. Wenn der Versuch zur Belegung der `HGLOBAL` ein Fehler auftritt, wird eine standard-Memory-Ausnahme ausgelöst.

Klassen-Assistent verbindet eine **SQL_LONGVARCHAR** oder **SQL_LONGVARBINARY** auf eine `CLongBinary` für Sie. Wählen Sie `CLongBinary` als Variablen im Dialogfeld "Hinzufügen von Membervariablen". Anschließend fügen Sie der Klassen-Assistent eine `RFX_LongBinary` aufrufen, um Ihre `DoFieldExchange` aufrufen und die Gesamtzahl der gebundene Felder erhöhen.

Um lange Daten Spaltenwerte zu aktualisieren, vergewissern Sie sich zunächst die zugeordnete `HGLOBAL` ist groß genug, um die neuen Daten durch Aufrufen von aufzunehmen **:: GlobalSize ist** auf die *M_hData* Mitglied der `CLongBinary`. Wenn es zu klein ist, Version der `HGLOBAL` , und ordnen Sie eine geeignete Größe. Legen Sie dann *M_dwDataLength* entsprechend die neue Größe.

Andernfalls gilt: Wenn *M_dwDataLength* ist größer als die Größe der Daten, die Sie ersetzen, können Sie entweder kostenlos sowie zum erneuten Zuweisen der `HGLOBAL`, oder lassen sie das zugeordnet. Vergewissern Sie sich an, dass die Anzahl der Bytes, die tatsächlich verwendeten *M_dwDataLength*.

## <a name="how-updating-a-clongbinary-works"></a>Beim Update ein CLongBinary funktioniert

Es ist nicht erforderlich, um zu verstehen wie aktualisieren eine `CLongBinary` funktioniert, aber es ist möglicherweise hilfreich, als ein Beispiel dazu, wie lange Datenwerte mit einer Datenquelle zu senden, wenn Sie diese dritte Methode, die unten beschriebenen auswählen.

> [!NOTE]
>  In der Reihenfolge für eine `CLongBinary` Feld in einem Update eingeschlossen werden müssen Sie explizit aufrufen `SetFieldDirty` für das Feld. Wenn Sie ein Feld, einschließlich des Setzens von Null, eine Änderung vornehmen müssen, rufen `SetFieldDirty`. Sie müssen auch aufrufen, `SetFieldNull`, wobei der zweite Parameter **"false"**, um das Feld einen Wert zu kennzeichnen.

Bei der Aktualisierung einer `CLongBinary` Feld der ODBC-Datenbankklassen verwendet werden **DATA_AT_EXEC** Mechanismus (finden Sie in ODBC-Dokumentation auf `SQLSetPos`des RgbValue-Argument). Wenn bereitet das Framework vor der INSERT- oder Update-Anweisung, anstatt auf die `HGLOBAL` mit den Daten, die *Adresse* von der `CLongBinary` festgelegt ist, als die *Wert* der Spalte Stattdessen, und legen Sie auf den Längenindikator **SQL_DATA_AT_EXEC**. Wenn die Update-Anweisung an die Datenquelle gesendet wird später `SQLExecDirect` zurück **SQL_NEED_DATA**. Dem Framework, dass der Wert von der Parameter für diese Spalte tatsächlich die Adresse des hingewiesen eine `CLongBinary`. Das Framework ruft `SQLGetData` erwartet einmal mit einem kleinen Puffer, den Treiber an, die tatsächliche Länge der Daten zurück. Wenn der Treiber die tatsächliche Länge des binary large Object (das BLOB) zurückgibt, zuordnet MFC so viel Speicherplatz wie erforderlich, um das BLOB abrufen. Wenn die Datenquelle gibt **SQL_NO_TOTAL**, gibt an, dass sie die Größe des BLOBs nicht bestimmen kann, wird MFC kleinere Blöcke erstellt. Die anfängliche Standardgröße ist 64 KB, und nachfolgende Blöcke werden doppelt so groß; Beispielsweise wird die zweite 128 k beträgt, das dritte hingegen ist 256K und So weiter. Die ursprüngliche Größe ist konfigurierbar.

## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Keine Bindung: Senden/Abrufen von Daten direkt aus ODBC mit SQLGetData

Mit dieser Methode Sie vollständig umgehen die Datenbankklassen und befassen sich mit der Spalte lange Daten selbst.

Vorteile:

Sie können Daten, um bei Bedarf auf den Datenträger, oder entscheiden dynamisch, wie viele Daten abrufen, Zwischenspeichern.

Nachteile:

Erhalten Sie nicht der Frameworks `Edit` oder `AddNew` Unterstützung, und Sie müssen schreiben code selbst zum Ausführen von grundlegenden Funktionen (`Delete` funktioniert jedoch, da es sich nicht um eine Spalte-Vorgang auf Taskebene ist).

In diesem Fall muss die long-Daten-Spalte in der select-Liste des Recordset-Objekts, jedoch nicht gebunden werden soll durch das Framework. Eine Möglichkeit, Sie ist, geben Sie eine eigene SQL-Anweisung über `GetDefaultSQL` oder als Argument LpszSQL `CRecordset`des `Open` Funktion, und die zusätzliche Spalte mit einem Funktionsaufruf RFX_ nicht bindet, bindet. ODBC benötigt die nicht gebundene Felder rechts neben der gebundene Felder angezeigt werden, fügen Sie daher Ihre ungebundenen Spalte oder Spalten an das Ende der select-Liste.

> [!NOTE]
>  Da die Spalte lange Daten nicht durch das Framework gebunden ist, Änderungen daran nicht verarbeitet mit `CRecordset::Update` aufrufen. Erstellen und senden Sie die erforderlichen SQL **einfügen** und **UPDATE** Anweisungen selbst.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
