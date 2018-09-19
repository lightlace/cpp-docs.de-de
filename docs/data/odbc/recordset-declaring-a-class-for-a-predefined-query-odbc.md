---
title: 'Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9161cccf9b3efd918f65ab2a703808041f3eb209
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113746"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)

Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
In diesem Thema wird erläutert, wie eine Recordsetklasse für eine vordefinierte Abfrage (manchmal auch als eine gespeicherte Prozedur, wie in Microsoft SQL Server bezeichnet) erstellt wird.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn massenzeilenabruf implementiert wird, ist der Prozess sehr ähnlich. Um zu verstehen, die Unterschiede zwischen Recordsets, gesammelte implementieren, und solche, die nicht der Fall ist, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
Einige Datenbank-Managementsystemen (DBMS) können Sie eine vordefinierte Abfrage erstellen und sie über Ihre Programme wie eine Funktion aufrufen. Die Abfrage hat einen Namen, ggf. die Parameter annehmen und Datensätze zurückgeben. In diesem Thema wird beschrieben, wie Sie eine vordefinierte Abfrage zu aufrufen, die Gibt Datensätze zurück (und möglicherweise mit Parametern) ausgeführt werden kann.  
  
Die Datenbankklassen unterstützen keine vordefinierte Abfragen aktualisieren. Der Unterschied zwischen einer vordefinierten Abfrage der Momentaufnahme und eine vordefinierte Abfrage von Dynaset ist nicht aktualisierbar, aber gibt an, ob Änderungen von anderen Benutzern (oder weitere Recordsets in Ihrem Programm) im Recordset angezeigt werden.  
  
> [!TIP]
>  Sie ist nicht erforderlich, dass ein Recordset eine vordefinierte Abfrage aufrufen, die keine Datensätze zurückgibt. Bereiten Sie die SQL-Anweisung wie im folgenden beschrieben vor, aber führen Sie es durch Aufrufen der `CDatabase` Memberfunktion [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
Sie können eine einzelne Recordset-Klasse zum Verwalten der Aufruf einer vordefinierten Abfrage erstellen, jedoch müssen Sie einige der Aufgaben selbst. Die Assistenten unterstützen das Erstellen einer Klasse speziell für diesen Zweck nicht.  
  
#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Zum Erstellen einer Klasse für den Aufruf einer vordefinierten Abfrage (gespeicherten Prozedur)  
  
1. Verwenden der [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** eine Recordset-Klasse für die Tabelle zu erstellen, die die Spalten, die von der Abfrage zurückgegebenen beiträgt. Dies bietet Ihnen einen raschen Einstieg.  
  
1. Fügen Sie manuell Felddatenmember für alle Spalten aller Tabellen, die die Abfrage zurückgibt, aber der Assistent keine für Sie erstellt haben.  
  
     Z. B. wenn der Abfrage drei Spalten aus zwei weitere Tabellen zurückgegeben, fügen Sie sechs Felddatenmembern (die entsprechenden Datentypen) der Klasse hinzu.  
  
1. Manuelles Hinzufügen [RFX](../../data/odbc/record-field-exchange-rfx.md) Funktionsaufrufe in der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Memberfunktion der Klasse, eine für den Datentyp der einzelnen hinzugefügt felddatenelement.  
  
    ```cpp  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Sie müssen die Datentypen und die Reihenfolge der Spalten im Ergebnis zurückgegeben, legen Sie kennen. Die Reihenfolge der RFX-Funktion aufruft, im `DoFieldExchange` muss die Reihenfolge der Spalten im Resultset entsprechen.  
  
1. Manuell fügen Sie Initialisierungen für den neuen Felddatenmembern in den Konstruktor des Recordset-Klasse hinzu.  
  
     Außerdem müssen Sie den Initialisierungswert erhöhen die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) -Datenmember. Schreibt die Initialisierung der Assistent zwar, enthält jedoch nur die Felddatenmembern, die es für Sie hinzufügt. Zum Beispiel:  
  
    ```cpp  
    m_nFields += 6;  
    ```  
  
     Einige Datentypen sollte nicht initialisiert werden, z. B. `CLongBinary` oder Bytearrays.  
  
1. Wenn die Abfrage Parameter akzeptiert, fügen Sie einen Datenmember "Parameter" für jeden Parameter, RFX-Funktion für jede und eine Initialisierung für jeden hinzu.  
  
1. Erhöhen Sie `m_nParams` für jeden Parameter, hinzugefügten wie Sie `m_nFields` für Felder in Schritt 4 dieses Verfahrens hinzugefügt. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
1. Schreiben Sie manuell eine SQL-Anweisung-Zeichenfolge im folgenden Format ein:  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     in denen **Aufrufen** ist ein ODBC-Schlüsselworts **Prozedurname** ist der Name der Abfrage wie in der Datenquelle bekannt ist und das "?" sind Platzhalter für die Parameterwerte, die Sie angeben, das Recordset zur Laufzeit (sofern vorhanden) . Im folgende Beispiel wird einen Platzhalter für einen Parameter vorbereitet:  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
1. In den Code, der das Recordset geöffnet wird, legen Sie die Werte des Recordsets Parameters-Datenmember und rufen Sie dann die `Open` Member-Funktion, die eine SQL-Zeichenfolge übergeben, für die *LpszSQL* Parameter. Oder Ersetzen Sie die Zeichenfolge, die zurückgegeben werden, indem Sie stattdessen die `GetDefaultSQL` Member-Funktion in Ihrer Klasse.  
  
Die folgenden Beispiele zeigen das Verfahren zum Aufruf einer vordefinierten Abfrage, mit dem Namen `Delinquent_Accts`, die nimmt einen Parameter für eine Reihe Verkaufsbereich. Diese Abfrage gibt drei Spalten zurück: `Acct_No`, `L_Name`, `Phone`. Alle Spalten stammen aus der Customers-Tabelle.  
  
Das folgende Recordset gibt Felddatenmember für die Spalten, die die Nummer der angeforderten Laufzeit der Abfrage zurückgegeben und einen Parameter für den Umsatz nach Region.  
  
```cpp  
class CDelinquents : public CRecordset  
{  
// Field/Param Data  
    LONG m_lAcct_No;  
    CString m_strL_Name;  
    CString m_strPhone;  
    LONG m_lDistParam;  
    // ...  
};  
```  
  
Diese Deklaration ist, wie Sie den Assistenten, mit Ausnahme von der `m_lDistParam` Member manuell hinzugefügt. Andere Mitglieder werden hier nicht angezeigt.  
  
Das nächste Beispiel zeigt, wie die für die Datenelemente in der `CDelinquents` Konstruktor.  
  
```cpp  
CDelinquents::CDelinquents(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
    // Wizard-generated params:  
    m_lAcct_No = 0;  
    m_strL_Name = "";  
    m_strPhone = "";  
    m_nFields = 3;  
    // User-defined params:  
    m_nParams = 1;  
    m_lDistParam = 0;  
}  
```  
  
Beachten Sie die Initialisierungen für [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) und [M_nParams](../../mfc/reference/crecordset-class.md#m_nparams). Der Assistent initialisiert `m_nFields`; Sie initialisieren `m_nParams`.  
  
Das nächste Beispiel zeigt die RFX-Funktionen in `CDelinquents::DoFieldExchange`:  
  
```cpp  
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)  
{  
    pFX->SetFieldType(CFieldExchange::outputColumn);  
    RFX_Long(pFX, "Acct_No", m_lAcct_No);  
    RFX_Text(pFX, "L_Name", m_strL_Name);  
    RFX_Text(pFX, "Phone", m_strPhone);  
    pFX->SetFieldType(CFieldExchange::param);  
    RFX_Long(pFX, "Dist_No", m_lDistParam);  
}  
```  
  
Neben den RFX Aufrufe für die drei zurückgegebenen Spalten, wird in diesem Code bindet den Parameter, die, den Sie zur Laufzeit übergeben. Der Parameter wird bestimmt, auf die `Dist_No` (Nummer)-Spalte.  
  
Das nächste Beispiel zeigt, wie Sie die SQL-Zeichenfolge einrichten und wie Sie es verwenden, um das Recordset geöffnet.  
  
```cpp  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
Dieser Code erstellt eine Momentaufnahme, übergibt sie einen Parameter, der zuvor vom Benutzer und ruft die vordefinierte Abfrage. Die Abfrage ausgeführt wird, gibt sie Einträge für den angegebenen Verkaufsbereich zurück. Jeder Datensatz enthält Spalten für die Kontonummer, Nachname des Kunden und die Telefonnummer des Kunden.  
  
> [!TIP]
>  Sie möchten einen Rückgabewert (Ausgabeparameter) aus einer gespeicherten Prozedur zu behandeln. Weitere Informationen und ein Beispiel finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
## <a name="see-also"></a>Siehe auch  

[Recordset (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Recordset: Ausführen eines Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)