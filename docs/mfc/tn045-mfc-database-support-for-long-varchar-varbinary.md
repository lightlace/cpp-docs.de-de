---
title: "TN045: MFC-Datenbankunterstützung für lange Varchar-Varbinary | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.data
dev_langs: C++
helpviewer_keywords:
- TN045
- Varbinary data type
- Varchar data type
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e1c9b64ef3b164c45a1633281bbaebd6525df659
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn045-mfcdatabase-support-for-long-varcharvarbinary"></a>TN045: MFC- und Datenbankunterstützung für LONGVARCHAR und LONGVARBINARY
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird beschrieben, wie zum Abrufen und senden die ODBC **SQL_LONGVARCHAR** und **SQL_LONGVARBINARY** Datenbank Datentypen mithilfe von MFC-Klassen.  
  
## <a name="overview-of-long-varcharvarbinary-support"></a>Übersicht über lange LONGVARBINARY-Unterstützung  
 Die ODBC **SQL_LONG_VARCHAR** und **SQL_LONGBINARY** Datentypen (wird hier als lange Datenspalten bezeichnet) große Mengen an Daten aufnehmen können. Es gibt 3 Arten Sie diese Daten behandeln können:  
  
-   Binden Sie es an einem `CString` / `CByteArray`.  
  
-   Binden Sie es an einem `CLongBinary`.  
  
-   Keine überhaupt zu binden Sie und rufen Sie ab und senden Sie den Wert der long-Daten manuell, unabhängig von den Datenbankklassen.  
  
 Jede der drei Methoden hat vor- und Nachteile.  
  
 Long-Daten-Spalten werden für die Parameter für eine Abfrage nicht unterstützt. Sie werden nur für OutputColumns unterstützt.  
  
## <a name="binding-a-long-data-column-to-a-cstringcbytearray"></a>Binden eine Spalte Long-Daten an eine CString/CByteArray  
 Vorteile:  
  
 Dieser Ansatz ist einfacher zu verstehen, und arbeiten Sie mit vertrauten Klassen. Das Framework bietet `CFormView` Unterstützung für `CString` mit `DDX_Text`. Sie haben viele allgemeine Funktionen, Zeichenfolge oder eine Auflistung mit den `CString` und `CByteArray` Klassen, und Sie können die Größe des Arbeitsspeichers, die lokal, um den Datenwert aufnehmen steuern. Das Framework verwaltet eine alte Exemplar der Feld-Daten während der **bearbeiten** oder `AddNew` Funktionsaufrufe und das Framework ist, können Änderungen an den Daten für Sie automatisch zu erkennen.  
  
> [!NOTE]
>  Da `CString` dient zum Zeichendaten, bearbeiten und `CByteArray` für binäre Daten arbeiten, wird empfohlen, die Zeichendaten zu speichern (**SQL_LONGVARCHAR**) in `CString`, und die binären Daten ( **SQL_LONGVARBINARY**) in `CByteArray`.  
  
 Der RFX-Funktionen für `CString` und `CByteArray` haben Sie ein zusätzliches Argument, und Sie können Sie die Standardgröße des belegten Speichers für den abgerufenen Wert für die Datenspalte außer Kraft setzen. Beachten Sie das Argument nMaxLength in den folgenden Deklarationen von Funktionen aus:  
  
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
  
 Wenn Sie eine Spalte long-Daten in Abrufen einer `CString` oder `CByteArray`, die maximal zurückgegebene Datenmenge ist standardmäßig 255 Bytes. Dies alles wird ignoriert. In diesem Fall löst das Framework der Ausnahme **AFX_SQL_ERROR_DATA_TRUNCATED**. Glücklicherweise können Sie explizit erhöhen nMaxLength auf größere Werte bis zu **MAXINT**.  
  
> [!NOTE]
>  Der Wert der nMaxLength wird von MFC verwendet, um den lokalen Puffer festgelegt die **SQLBindColumn** Funktion. Dies ist der lokale Puffer zum Speichern der Daten und tatsächlich wirkt sich nicht die Menge der Daten, die vom ODBC-Treiber zurückgegeben. `RFX_Text`und `RFX_Binary` stellen nur eine rufen **SQLFetch** zum Abrufen der Daten aus der Back-End-Datenbank. Jede ODBC-Treiber hat eine andere Einschränkung auf die Menge der Daten, die in einer einzigen Abfrage zurückgegeben werden können. Dieser Grenzwert ist möglicherweise wesentlich kleiner als der Wert in nMaxLength, in dem Fall wird die Ausnahme **AFX_SQL_ERROR_DATA_TRUNCATED** ausgelöst. Unter diesen Umständen wird zur Verwendung von wechseln `RFX_LongBinary` anstelle von `RFX_Text` oder `RFX_Binary` , damit alle Daten abgerufen werden können.  
  
 ClassWizard verbindet einen **SQL_LONGVARCHAR** auf eine `CString`, oder ein **SQL_LONGVARBINARY** auf eine `CByteArray` für Sie. Wenn Sie mehr als 255 Byte zuweisen, in denen Sie die Spalte long-Daten abrufen, möchten, können Sie dann einen expliziten Wert für nMaxLength angeben.  
  
 Wenn eine lange Spalte gebunden ist, um eine `CString` oder `CByteArray`, aktualisieren das Feld genauso wie bei der Bindung an eine SQL_ funktioniert**VARCHAR** oder SQL_**VARBINARY**. Während der **bearbeiten**, unterwegs und höher verglichen, wenn der Datenwert zwischengespeichert **Update** wird aufgerufen, um Änderungen an den Daten Wert und die Dirty festgelegt und Null-Werte für die Spalte ordnungsgemäß zu erkennen.  
  
## <a name="binding-a-long-data-column-to-a-clongbinary"></a>Binden eine Spalte Long-Daten an eine CLongBinary  
 Wenn die Spalte long-Daten mehr enthalten möglicherweise **"maxint" identisch** Datenbytes, wahrscheinlich sollten Sie es in Abrufen einer `CLongBinary`.  
  
 Vorteile:  
  
 Dies ruft eine gesamte long-Daten-Spalte, bis zu den verfügbaren Arbeitsspeicher ab.  
  
 Nachteile:  
  
 Die Daten werden im Speicher gehalten werden. Diese Vorgehensweise ist auch für sehr große Datenmengen ungeheuer teuer. Rufen Sie `SetFieldDirty` Member, um sicherzustellen, dass das Feld dient für die gebundenen Daten in einem **Update** Vorgang.  
  
 Wenn Abrufen von long-Daten-Spalten in einer `CLongBinary`, Datenbankklassen überprüfen Sie die Gesamtgröße der Spalte long-Daten werden dann belegen eine `HGLOBAL` Speichersegment groß genug ist, um den gesamten Datenwert zu speichern. Die Datenbankklassen abrufen klicken Sie dann den gesamten Datenwert in der zugeordneten `HGLOBAL`.  
  
 Wenn die Datenquelle die erwartete Größe der Spalte long-Daten zurückgeben kann, löst das Framework die Ausnahme **AFX_SQL_ERROR_SQL_NO_TOTAL**. Wenn der Versuch, belegen die `HGLOBAL` ein Fehler auftritt, eine standard Speicherausnahme wird ausgelöst.  
  
 ClassWizard verbindet ein **SQL_LONGVARCHAR** oder **SQL_LONGVARBINARY** zu einem `CLongBinary` für Sie. Wählen Sie `CLongBinary` als den Variablentyp im Dialogfeld "Hinzufügen von Membervariablen". ClassWizard anschließend fügen Sie ein `RFX_LongBinary` aufrufen, um Ihre `DoFieldExchange` aufrufen und erhöht die Gesamtzahl der gebundenen Felder.  
  
 Um lange Daten Spaltenwerte zu aktualisieren, vergewissern Sie sich zunächst die zugeordnete `HGLOBAL` ist groß genug für die neuen Daten durch den Aufruf **:: GlobalSize ist** auf die `m_hData` Mitglied der `CLongBinary`. Wenn es zu klein ist, Version der `HGLOBAL` , und weisen Sie eine angemessene Größe. Legen Sie dann `m_dwDataLength` entsprechend die neue Größe.  
  
 Andernfalls gilt: Wenn `m_dwDataLength` ist größer als die Größe der Daten, die Sie ersetzen, können Sie entweder frei und weisen die `HGLOBAL`, oder lassen Sie ihn zugeordnet. Vergewissern Sie sich an, dass die Anzahl der Bytes, die tatsächlich verwendeten `m_dwDataLength`.  
  
## <a name="how-updating-a-clongbinary-works"></a>Wie Aktualisieren einer CLongBinary funktioniert  
 Es ist nicht erforderlich, um zu verstehen, wie Aktualisieren einer `CLongBinary` funktioniert, aber es ist möglicherweise hilfreich, als ein Beispiel dafür, wie lange Datenwerte mit einer Datenquelle zu senden, wenn Sie diese dritte Methode, die unten beschriebenen auswählen.  
  
> [!NOTE]
>  In der Reihenfolge für eine `CLongBinary` Feld, die in einem Update eingeschlossen werden müssen Sie explizit aufrufen `SetFieldDirty` für das Feld. Wenn Sie ein Feld, einschließlich dem Festlegen von Null, Änderungen vornehmen müssen, rufen `SetFieldDirty`. Sie müssen auch aufrufen, `SetFieldNull`, wobei der zweite Parameter **"false"**, um das Feld als hätte es den Wert zu markieren.  
  
 Beim Aktualisieren einer `CLongBinary` Feld der ODBC-Datenbankklassen verwendet werden **DATA_AT_EXEC** Mechanismus (finden Sie in ODBC-Dokumentation auf **SQLSetPos**des RgbValue-Argument). Beim bereitet das Framework vor der INSERT- oder Update-Anweisung, statt auf die `HGLOBAL` mit den Daten der *Adresse* von der `CLongBinary` festgelegt ist, als die *Wert* der Spalte Stattdessen und den Längenindikator, legen Sie auf **SQL_DATA_AT_EXEC**. Wenn die Update-Anweisung an die Datenquelle gesendet wird später **SQLExecDirect** zurück **SQL_NEED_DATA**. Dies weist dem Framework, dass der Wert von den Parametern für diese Spalte tatsächlich die Adresse des eine `CLongBinary`. Das Framework ruft **SQLGetData** einmal mit einem kleinen Puffer, erwartet des Treibers, um die tatsächliche Länge der Daten zurückzugeben. Wenn der Treiber die tatsächliche Länge der binary large Object (BLOB) zurückgibt, zuordnet MFC so viel Speicherplatz wie erforderlich, um das BLOB abzurufen. Wenn die Datenquelle gibt **SQL_NO_TOTAL**, gibt an, dass nicht die Größe des BLOB bestimmt werden kann, wird MFC kleinere Blöcke erstellen. Die anfängliche Standardgröße beträgt 64 KB und nachfolgende Blöcke ist doppelt so groß werden. Beispielsweise ist die zweite 128 KB, der dritte ist 256K und So weiter. Die Anfangsgröße ist konfigurierbar.  
  
## <a name="not-binding-retrievingsending-data-directly-from-odbc-with-sqlgetdata"></a>Keine Bindung: Abrufen von/Senden von Daten direkt aus ODBC mit SQLGetData  
 Mit dieser Methode Sie vollständig Datenbankklassen umgehen und nur die Daten vom Typ long-Spalte selbst.  
  
 Vorteile:  
  
 Daten, die bei Bedarf auf den Datenträger oder dynamisch, wie viele Daten abrufen entscheiden können zwischengespeichert werden.  
  
 Nachteile:  
  
 Erhalten Sie nicht des Frameworks **bearbeiten** oder `AddNew` unterstützt, und Sie müssen schreiben code selbst, um grundlegende Funktionen auszuführen (**löschen** funktioniert jedoch, da er sich nicht um eine spaltenvorgang auf Systemebene ist).  
  
 In diesem Fall die long-Datenspalte in der select-Liste des Recordsets werden muss, jedoch nicht gebunden werden soll durch das Framework. Lässt sich beispielsweise erreichen dies ist über eine eigene SQL-Anweisung angeben `GetDefaultSQL` oder als Argument LpszSQL `CRecordset`des **öffnen** -Funktion und die zusätzliche Spalte mit einem Funktionsaufruf RFX_ nicht gebunden werden. ODBC ist erforderlich, gebundene Felder rechts ungebundenes Felder angezeigt werden, also den ungebundenen Spalte oder Spalten am Ende der select-Liste hinzufügen.  
  
> [!NOTE]
>  Da die Spalte long-Daten nicht durch das Framework gebunden ist, Änderungen an den er nicht verarbeitet mit `CRecordset::Update` aufrufen. Müssen Sie erstellen und senden Sie die erforderliche SQL **einfügen** und **UPDATE** Anweisungen selbst.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

