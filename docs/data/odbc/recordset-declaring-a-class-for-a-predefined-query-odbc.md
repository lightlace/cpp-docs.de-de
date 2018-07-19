---
title: 'Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC) | Microsoft Docs'
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
ms.openlocfilehash: cbbb9202aaf56681a792e1acf2a0c02eff5636d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092374"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Recordset: Deklarieren einer Klasse für eine vordefinierte Abfrage (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie eine Recordsetklasse für eine vordefinierte Abfrage (mitunter als eine gespeicherte Prozedur, wie in Microsoft SQL Server) erstellt wird.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn gesammelte implementiert wird, ist der Prozess sehr ähnlich. Die Unterschiede zwischen Recordsets, die gesammelte implementieren, und solche, die nicht der Fall, erfahren Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Einige Datenbank-Managementsystemen (DBMS) können Sie eine vordefinierte Abfrage erstellen und aus Ihren Programmen wie eine Funktion aufgerufen wird. Die Abfrage hat einen Namen, möglicherweise Parameter annehmen und möglicherweise Datensätze zurück. In diesem Thema wird beschrieben, wie eine vordefinierte Abfrage aufrufen, die Datensätze zurück (und möglicherweise mit Parametern) ausgeführt werden kann.  
  
 Die Datenbankklassen unterstützen keine vordefinierte Abfragen aktualisieren. Der Unterschied zwischen einer vordefinierten Abfrage der Momentaufnahme und eine vordefinierte Dynaset-Abfrage ist nicht aktualisierbar, aber gibt an, ob von anderen Benutzern (oder andere Recordsets in Ihrem Programm) vorgenommene Änderungen im Recordset angezeigt werden.  
  
> [!TIP]
>  Sie ist nicht erforderlich, dass ein Recordset eine vordefinierte Abfrage aufrufen, die keinen Datensätze zurückgibt. Bereiten Sie die SQL-Anweisung wie nachfolgend beschrieben vor, aber führen Sie es durch Aufrufen der `CDatabase` Memberfunktion [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
 Sie können eine einzelne Recordset-Klasse zum Verwalten der Aufruf einer vordefinierten Abfrage erstellen, aber Sie müssen Teil der Arbeit selbst. Erstellen einer Klasse speziell für diesen Zweck unterstützt die Assistenten nicht.  
  
#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>So erstellen eine Klasse für eine vordefinierte Abfrage aufrufen gespeicherte (Prozedur)  
  
1.  Verwenden der [MFC-ODBC-Consumer-Assistent](../../mfc/reference/adding-an-mfc-odbc-consumer.md) aus **Klasse hinzufügen** eine Recordsetklasse für die Tabelle erstellen, die die meisten Spalten, die von der Abfrage zurückgegebenen beiträgt. Dies gibt Ihnen einen Vorsprung.  
  
2.  Fügen Sie manuell Felddatenmember für alle Spalten aller Tabellen, die die Abfrage zurückgibt, aber, dass der Assistent nicht für Sie erstellt haben.  
  
     Z. B. wenn die Abfrage drei Spalten aus zwei zusätzliche Tabellen zurückgibt, fügen Sie sechs Felddatenmember (der entsprechenden Datentypen hinzu) der Klasse.  
  
3.  Manuell hinzufügen [RFX](../../data/odbc/record-field-exchange-rfx.md) -Funktionsaufrufe in der [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) Memberfunktion der Klasse, für den Datentyp der einzelnen hinzugefügt felddatenelement.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Sie müssen die Datentypen und die Reihenfolge der Spalten im Resultset zurückgegebenen festgelegt kennen. Die Reihenfolge der RFX-Aufrufe `DoFieldExchange` muss die Reihenfolge der Spalten im Resultset entsprechen.  
  
4.  Fügen Sie manuell Initialisierungen für den neuen Felddatenmembern im Konstruktor Recordset-Klasse hinzu.  
  
     Außerdem müssen Sie den Initialisierungswert erhöhen die [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) -Datenmember. Schreibt der Assistent die Initialisierung, enthält jedoch nur die Felddatenmembern, die sie hinzugefügt wird. Zum Beispiel:  
  
    ```  
    m_nFields += 6;  
    ```  
  
     Einige Datentypen sollte nicht initialisiert werden, z. B. `CLongBinary` oder Bytearrays.  
  
5.  Wenn die Abfrage Parameter akzeptiert, fügen Sie einen Parameterdatenmember für jeden Parameter, RFX-Funktion für jede und eine Initialisierung für jede hinzu.  
  
6.  Erhöhen Sie `m_nParams` für jeden Parameter, wie bei der hinzugefügten `m_nFields` für Felder in Schritt 4 dieses Verfahrens hinzugefügt. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
7.  Schreiben Sie manuell eine SQL-Anweisungszeichenfolge mit der folgenden Form:  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     auf dem **Aufrufen** ist ein ODBC-Schlüsselwort, **Proc-Name** ist der Name der Abfrage, da es in der Datenquelle bekannt ist und die "?" sind Platzhalter für Parameterwerte, die Sie angeben, das Recordset zur Laufzeit (sofern vorhanden) . Im folgende Beispiel wird einen Platzhalter für einen Parameter vorbereitet:  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  In den Code, der das Recordset geöffnet wird, legen Sie die Werte des Parameters für das Recordset-Datenmember und rufen Sie anschließend die **öffnen** Memberfunktion ist, übergeben eine SQL-Zeichenfolge für die **LpszSQL** Parameter. Oder Ersetzen Sie die Zeichenfolge, die zurückgegeben werden, indem Sie stattdessen die `GetDefaultSQL` Memberfunktion in Ihrer Klasse.  
  
 Die folgenden Beispiele zeigen das Verfahren zum Aufrufen einer vordefinierten Abfrage mit dem Namen `Delinquent_Accts`, dem nimmt einen Parameter für eine Reihe Verkaufsbereich. Diese Abfrage gibt drei Spalten zurück: `Acct_No`, `L_Name`, `Phone`. Alle Spalten werden aus der Customers-Tabelle.  
  
 Das folgende Recordset gibt Felddatenmember für die Spalten, die der Abfrage zurückgegeben und einen Parameter für das Sales zur Laufzeit angeforderte Anzahl District.  
  
```  
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
  
 Diese Klassendeklaration wird wie der Assistent, mit Ausnahme von schreibt die `m_lDistParam` manuell hinzugefügte Element. Andere Member werden hier nicht angezeigt.  
  
 Das nächste Beispiel zeigt, wie die Datenelemente in der `CDelinquents` Konstruktor.  
  
```  
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
  
```  
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
  
 Dieser Code verwaltet neben der RFX-Aufrufe für die drei zurückgegebenen Spalten vornimmt, Binden des Parameters, den Sie zur Laufzeit übergeben. Der Parameter wird sortiert, um die `Dist_No` (Nummer)-Spalte.  
  
 Das nächste Beispiel zeigt, wie Sie die SQL-Zeichenfolge einrichten und Gewusst wie: Verwenden Sie zum Öffnen des Recordsets.  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 Dieser Code erstellt eine Momentaufnahme, übergibt es einen Parameter, die zuvor vom Benutzer erhaltenes und ruft die vordefinierte Abfrage. Wenn die Abfrage ausgeführt wird, zurück es Datensätze für den angegebenen Verkaufsbereich. Jeder Datensatz enthält Spalten für die Kontonummer, Nachnamen des Kunden und Telefonnummer des Kunden.  
  
> [!TIP]
>  Sie möchten einen Rückgabewert (Ausgabeparameter) von einer gespeicherten Prozedur zu behandeln. Weitere Informationen und ein Beispiel finden Sie unter [CFieldExchange::](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Erneutes Abfragen eines Recordsets (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset: Ausführen eines Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)