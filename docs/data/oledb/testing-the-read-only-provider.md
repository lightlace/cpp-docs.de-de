---
title: "Testen des schreibgesch&#252;tzten Anbieters"
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
  - "OLE DB-Anbieter, Aufrufen"
  - "OLE DB-Anbieter, Testen"
  - "Testen von Anbietern"
  - "Testen, OLE DB-Anbieter"
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Testen des schreibgesch&#252;tzten Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie benötigen einen Consumer, um den Anbieter zu testen.  Es ist von Vorteil, wenn die Funktionen von Consumer und Anbieter aufeinander abgestimmt sind.  Die OLE DB\-Consumervorlagen bilden einen einfachen Wrapper für OLE DB und sind auf die Anbieter\-COM\-Objekte abgestimmt.  Da der Quellcode mit den Consumervorlagen ausgeliefert wird, ist ein Anbieter mithilfe der Vorlagen problemlos zu debuggen.  Außerdem bieten die Consumervorlagen eine schnelle, effiziente Methode zum Entwickeln von Consumeranwendungen.  
  
 In dem unter diesem Thema aufgeführten Beispiel wird eine Standardanwendung im Stil eines MFC\-Anwendungs\-Assistenten für einen Testconsumer erstellt.  Die Testanwendung ist ein einfaches Dialogfeld, dem OLE DB\-Consumervorlagencode hinzugefügt wurde.  
  
### So erstellen Sie die Testanwendung  
  
1.  Klicken Sie im Menü **Datei** erst auf **Neu** und dann auf **Projekt**.  
  
2.  Wählen Sie im Bereich Projekttypen den Ordner **Visual C\+\+\-Projekte** aus.  Klicken Sie im Bereich Vorlagen auf **MFC\-Anwendung**.  
  
3.  Geben Sie **TestProv** als Projektnamen ein, und klicken Sie auf **OK**.  
  
     Der MFC\-Anwendungs\-Assistent wird geöffnet.  
  
4.  Wählen Sie auf der Seite **Anwendungstyp** die Option **Auf Dialogfeldern basierend** aus.  
  
5.  Wählen Sie auf der Seite **Erweiterte Features** die Option **Automatisierung** aus, und klicken Sie dann auf **Fertig stellen**.  
  
> [!NOTE]
>  Wenn Sie **CoInitialize** in **CTestProvApp::InitInstance** einfügen, benötigt die Anwendung keine Automatisierungsunterstützung.  
  
 Sie können das Dialogfeld **TestProv** \(**IDD\_TESTPROV\_DIALOG**\) anzeigen und bearbeiten, indem Sie es in der Ressourcenansicht auswählen.  Fügen Sie zwei Listenfelder, d. h. eines für jede Zeichenfolge im Rowset, in das Dialogfeld ein.  Deaktivieren Sie die Sortierfunktion für beide Listenfelder, indem Sie, während das jeweilige Listenfeld markiert ist, ALT\+EINGABETASTE drücken, auf die Registerkarte **Formate** klicken und das Kontrollkästchen **Sortieren** deaktivieren.  Fügen Sie außerdem eine Schaltfläche **Ausführen** in das Dialogfeld ein, damit die Datei abgerufen werden kann.  Das fertige Dialogfeld TestProv sollte über zwei Listenfelder mit der Beschriftung "String 1" bzw. "String 2" sowie über die Schaltflächen **OK**, **Abbrechen** und **Ausführen** verfügen.  
  
 Öffnen Sie die Headerdatei für die Dialogfeldklasse \(in diesem Fall TestProvDlg.h\).  Fügen Sie der Headerdatei \(außerhalb eventuell vorkommender Klassendeklarationen\) den folgenden Code hinzu:  
  
```  
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 Der Code stellt einen Benutzerdatensatz dar, durch den die im Rowset enthaltenen Spalten definiert werden.  Beim Aufruf von **IAccessor::CreateAccessor** verwendet der Client diese Einträge, um die zu bindenden Spalten festzulegen.  Die OLE DB\-Consumervorlagen unterstützen auch das dynamische Binden von Spalten.  Bei den `COLUMN_ENTRY`\-Makros handelt es sich um die Clientversion der `PROVIDER_COLUMN_ENTRY`\-Makros.  Mithilfe der beiden `COLUMN_ENTRY`\-Makros werden Ordnungszahl, Länge und Datenmember für die beiden Zeichenfolgen angegeben.  
  
 Fügen Sie eine Handlerfunktion für die Schaltfläche **Ausführen** hinzu, indem Sie STRG drücken und auf die Schaltfläche **Ausführen** doppelklicken.  Fügen Sie folgenden Code in die Funktion ein:  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 Die Klassen `CCommand`, `CDataSource` und `CSession` gehören alle zu den OLE DB\-Consumervorlagen.  Durch jede Klasse wird ein COM\-Objekt im Anbieter imitiert.  Das `CCommand`\-Objekt akzeptiert die in der Headerdatei deklarierte `CProvider`\-Klasse als Vorlagenparameter.  Der `CProvider`\-Parameter entspricht den Bindungen, die Sie für den Zugriff auf die Anbieterdaten verwenden.  Dies ist der `Open` Code für Datenquelle, Sitzung und Befehl:  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 Durch die Zeilen zum Öffnen der einzelnen Klassen wird das jeweilige COM\-Objekt im Anbieter erstellt.  Der Anbieter wird anhand seiner Programm\-ID lokalisiert.  Sie können die Programm\-ID aus der Systemregistrierung oder anhand der Datei **MyProvider.rgs** ermitteln \(indem Sie das Anbieterverzeichnis öffnen und nach dem **ProgID**\-Schlüssel suchen\).  
  
 Die Datei MyData.txt ist im Beispiel MyProv enthalten.  Um eine eigene Datei zu erstellen, geben Sie eine gerade Anzahl von Zeichenfolgen in einem Editor ein und drücken nach jeder Zeichenfolge die EINGABETASTE.  Wenn Sie diese Datei verschieben, müssen Sie die Pfadangaben ändern.  
  
 Übergeben Sie die Zeichenfolge "c:\\\\samples\\\\myprov\\\\MyData.txt" in der `table.Open`\-Zeile.  Wenn Sie den `Open`\-Aufruf schrittweise prüfen, werden Sie feststellen, dass diese Zeichenfolge an die `SetCommandText`\-Methode im Anbieter übergeben wird.  Beachten Sie, dass diese Zeichenfolge von der `ICommandText::Execute`\-Methode verwendet wurde.  
  
 Zum Abrufen der Daten rufen Sie `MoveNext` für die Tabelle auf.  Durch `MoveNext` werden die Funktionen **IRowset::GetNextRows**, `GetRowCount` und `GetData` aufgerufen.  Wenn keine weiteren Zeilen vorhanden sind \(d. h., die aktuelle Position im Rowset ist größer als `GetRowCount`\), wird die Schleife beendet:  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Beachten Sie, dass Anbieter **DB\_S\_ENDOFROWSET** zurückgeben, sobald keine weiteren Zeilen mehr vorhanden sind.  Der **DB\_S\_ENDOFROWSET**\-Wert stellt keinen Fehler dar.  Um eine Datenabrufschleife zu beenden, sollten Sie stets `S_OK` gegenprüfen, anstatt das **SUCCEEDED**\-Makro zu verwenden.  
  
 Jetzt sollte es möglich sein, das Programm zu erstellen und zu testen.  
  
## Siehe auch  
 [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)