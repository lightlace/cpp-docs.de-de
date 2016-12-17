---
title: "Recordset: Deklarieren einer Klasse f&#252;r eine vordefinierte Abfrage (ODBC)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Recordsets, Abfragen"
  - "Vordefinierte Abfragen und Recordsets"
  - "Recordsets, Vordefinierte Abfragen"
  - "Recordsets, Gespeicherte Prozeduren"
  - "Gespeicherte Prozeduren, Und Recordsets"
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Deklarieren einer Klasse f&#252;r eine vordefinierte Abfrage (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird erläutert, wie Sie eine Recordset\-Klasse für eine vordefinierte Abfrage erstellen. Vordefinierte Abfragen werden manchmal, wie auch in Microsoft SQL Server, als "gespeicherte Prozedur" bezeichnet.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Falls das gesammelte Abrufen von Zeilen implementiert ist, ist der Prozess sehr ähnlich.  Eine Erläuterung der Unterschiede zwischen Recordsets, die das gesammelte Abrufen von Zeilen implementieren, und solchen, bei denen dies nicht der Fall ist, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 In manchen Datenbank\-Management\-Systemen \(DBMS\) können Sie eine vordefinierte Abfrage erstellen und diese vom Programm aus wie eine Funktion aufrufen.  Die Abfrage verfügt über einen Namen, kann mit Parametern versehen werden und Datensätze zurückgeben.  In diesem Thema wird beschrieben, wie Sie eine vordefinierte Abfrage aufrufen, die Datensätze zurückgibt und möglicherweise mit Parametern ausgeführt werden kann.  
  
 Die Datenbankklassen bieten keine Unterstützung für das Aktualisieren vordefinierter Abfragen.  Der Unterschied zwischen einer vordefinierten Momentaufnahme\-Abfrage und einer vordefinierten Dynaset\-Abfrage liegt nicht in der Aktualisierbarkeit, sondern darin, ob von anderen Benutzern oder anderen Recordsets innerhalb des Programms vorgenommene Änderungen im Recordset angezeigt werden.  
  
> [!TIP]
>  Sie benötigen kein Recordset, um eine vordefinierte Abfrage aufzurufen, die keine Datensätze zurückgibt.  Bereiten Sie die SQL\-Anweisung wie im folgenden Abschnitt beschrieben vor, aber führen Sie sie dadurch aus, dass Sie die `CDatabase`\-Memberfunktion [ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md) aufrufen.  
  
 Sie können eine einzelne Recordset\-Klasse erstellen, um den Aufruf einer vordefinierten Abfrage zu verwalten, einen Teil der Arbeit müssen Sie jedoch selbst durchführen.  Die Assistenten bieten keine Unterstützung zur Erstellung einer speziell für diesen Zweck geeigneten Klasse.  
  
#### So erstellen Sie eine Klasse für den Aufruf einer vordefinierten Abfrage \(gespeicherten Prozedur\)  
  
1.  Verwenden Sie den [MFC\-ODBC\-Consumer\-Assistenten](../../mfc/reference/adding-an-mfc-odbc-consumer.md) unter **Klasse hinzufügen**, um eine Recordset\-Klasse für die Tabelle zu erstellen, aus der die meisten durch die Abfrage zurückgegebenen Spalten stammen.  Somit wurde bereits ein Großteil der Arbeit durchgeführt.  
  
2.  Fügen Sie Felddatenmember manuell für die Spalten aller Tabellen hinzu, die von der Abfrage zurückgegeben werden, die der Assistent jedoch nicht erstellt hat.  
  
     Falls die Abfrage z. B. aus zwei zusätzlichen Tabellen jeweils drei Spalten zurückgibt, fügen Sie sechs Felddatenmember der entsprechenden Datentypen in die Klasse ein.  
  
3.  Fügen Sie manuell [RFX](../../data/odbc/record-field-exchange-rfx.md)\-Funktionsaufrufe in der [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)\-Memberfunktion der Klasse hinzu, und zwar je einen für jeden Datentyp der hinzugefügten Felddatenmember.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Sie müssen den Datentyp und die Reihenfolge der Spalten kennen, die in dem Resultset zurückgegeben werden.  Die Reihenfolge der RFX\-Funktionsaufrufe in `DoFieldExchange` muss der Reihenfolge der Spalten im Resultset entsprechen.  
  
4.  Fügen Sie von Hand Initialisierungen für die neuen Felddatenmember in den Konstruktor der Recordset\-Klasse ein.  
  
     Außerdem müssen Sie den Initialisierungswert des [m\_nFields](../Topic/CRecordset::m_nFields.md)\-Datenmembers erhöhen.  Der Assistent schreibt die Initialisierung, er zählt aber nur die Felddatenmember, die er selbst eingefügt hat.  Beispiel:  
  
    ```  
    m_nFields += 6;  
    ```  
  
     Manche Datentypen dürfen Sie hier nicht initialisieren. Dies sind z. B. `CLongBinary` oder Byte\-Arrays.  
  
5.  Falls die Abfrage Parameter unterstützt, fügen Sie für jeden Parameter einen Parameterdatenmember hinzu, rufen eine RFX\-Funktion auf und initialisieren ihn.  
  
6.  Erhöhen Sie `m_nParams` für jeden hinzugefügten Parameter, wie Sie dies im Schritt 4 für `m_nFields` durchgeführt haben.  Weitere Informationen hierzu finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
7.  Erstellen Sie von Hand eine SQL\-Anweisungszeichenfolge mit dem folgenden Format:  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     Hierbei handelt es sich bei **CALL** um ein ODBC\-Schlüsselwort, **proc\-name** ist der Name der Abfrage, die in der Datenquelle verzeichnet ist, und die "?"\-Elemente sind Platzhalter für Parameterwerte, die Sie dem Recordset zur Laufzeit bereitstellen.  Im folgenden Beispiel wird ein Platzhalter für einen Parameter vorbereitet:  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  Im Code zum Öffnen des Recordsets stellen Sie die Werte der Parameterdatenmember des Recordsets ein und rufen dann die **Open**\-Memberfunktion auf, der Sie die SQL\-Zeichenfolge für den **lpszSQL**\-Parameter übergeben.  Alternativ können Sie auch die Zeichenfolge ersetzen, die von der `GetDefaultSQL`\-Memberfunktion der Klasse zurückgegeben wird.  
  
 Die folgenden Beispiele zeigen den Aufruf einer vordefinierten Abfrage mit dem Namen `Delinquent_Accts`, die einen Parameter mit der Nummer des Vertriebsbereichs unterstützt.  Diese Abfrage gibt drei Spalten zurück: `Acct_No`, `L_Name` und `Phone`.  Alle Spalten stammen aus der Customers\-Tabelle.  
  
 Das folgende Recordset deklariert Felddatenmember für die Spalten, die von der Abfrage zurückgegeben werden, sowie einen Parameter für die Nummer des Vertriebsbereichs, die zur Laufzeit eingegeben wird.  
  
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
  
 Diese Klassendeklaration wird bis auf den Datenmember `m_lDistParam` so dargestellt, wie sie durch den Assistenten erstellt wurde.  Andere Member werden nicht hier angezeigt.  
  
 Das nächste Beispiel zeigt, wie die Datenmember im `CDelinquents`\-Konstruktor initialisiert werden.  
  
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
  
 Beachten Sie die Initialisierungen für [nFields](../Topic/CRecordset::m_nFields.md) und [m\_nParams](../Topic/CRecordset::m_nParams.md).  Der Assistent initialisiert `m_nFields`; Sie initialisieren `m_nParams`.  
  
 Das nächste Beispiel zeigt die RFX\-Funktionen in `CDelinquents::DoFieldExchange`:  
  
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
  
 Neben den RFX\-Aufrufen für die drei zurückgegebenen Spalten wird in diesem Code der zur Laufzeit bereitgestellte Parameter gebunden.  Der Parameter wird mit der `Dist_No`\-Spalte \(Nummer des Vertriebsbereichs\) verknüpft.  
  
 Das nächste Beispiel zeigt, wie Sie die SQL\-Zeichenfolge einstellen und damit das Recordset öffnen.  
  
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
  
 Dieser Code konstruiert eine Momentaufnahme, übergibt dieser einen vom Benutzer eingegebenen Parameterwert und ruft die vordefinierte Abfrage auf.  Wenn die Abfrage ausgeführt wird, gibt sie Datensätze des angegebenen Vertriebsbereichs zurück.  Jeder Datensatz enthält Spalten mit der Kontonummer, dem Nachnamen des Kunden und seiner Telefonnummer.  
  
> [!TIP]
>  Manchmal müssen Sie den Rückgabewert \(Ausgabeparameter\) einer gespeicherten Prozedur verarbeiten.  Weitere Informationen und ein Beispiel hierzu finden Sie unter [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Erneutes Abfragen eines Recordsets \(ODBC\)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [Recordset: Deklarieren einer Klasse für eine Tabelle \(ODBC\)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Recordset: Ausführen einer Verknüpfung \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)