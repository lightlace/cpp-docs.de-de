---
title: "Testen des schreibgeschützten Anbieters | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad2cf102902f62d03d4027c16b7d81b255b85875
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="testing-the-read-only-provider"></a>Testen des schreibgeschützten Anbieters
Um einen Anbieter zu testen, benötigen Sie einen Consumer. Es ist hilfreich, wenn der Consumer mit dem Anbieter übereinstimmen kann. Der OLE DB-Consumervorlagen werden ein schlanker Wrapper für OLE DB und übereinstimmen, mit dem Anbieter-COM-Objekten. Da die Quelle mit den Consumervorlagen ausgeliefert wird, ist es einfach, einen Anbieter mit dem sie debuggen. Die Consumervorlagen werden auch sehr klein und schnelle Möglichkeit, Consumer-Anwendungen zu entwickeln.  
  
 Im Beispiel in diesem Thema erstellt eine Standard-MFC-Anwendung-Assistent-Anwendung für einen Testconsumer an. Die testanwendung ist ein einfaches Dialogfeld mit OLE DB-Consumer-Vorlagencode hinzugefügt.  
  
### <a name="to-create-the-test-application"></a>So erstellen die testanwendung  
  
1.  Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
2.  Wählen Sie im Bereich Projekttypen den **Visual C++-Projekte** Ordner. Wählen Sie im Vorlagenbereich **MFC-Anwendung**.  
  
3.  Geben Sie für den Projektnamen **TestProv**, und klicken Sie dann auf **OK**.  
  
     Der MFC-Anwendung-Assistent wird angezeigt.  
  
4.  Auf der **Anwendungstyp** Seite **Dialogfeldern basierend**.  
  
5.  Auf der **erweiterte Funktionen** Seite **Automatisierung**, und klicken Sie dann auf **Fertig stellen**.  
  
> [!NOTE]
>  Die Anwendung erfordert keine-Unterstützung, wenn Sie hinzufügen **CoInitialize** in **CTestProvApp::InitInstance**.  
  
 Sie können anzeigen und bearbeiten das Dialogfeld TestProv (IDD_TESTPROV_DIALOG) dazu in der Ressourcenansicht. Platzieren Sie zwei Listenfelder, eines für jede Zeichenfolge im Rowset wird im Dialogfeld ein. Für beide Listenfelder durch Drücken von ALT + Eingabe, wenn ein Listenfeld ausgewählt ist, auf die Sortiereigenschaft Deaktivieren der **Stile** Registerkarte und das Löschen der **sortieren** Kontrollkästchen. Fügen Sie außerdem eine **ausführen** Schaltfläche auf das Dialogfeld, um die Datei abzurufen. Das Dialogfeld nicht mehr benötigen TestProv sollten zwei Listenfelder, die mit der Bezeichnung "String 1" und "String 2", verfügen. Sie hat auch **OK**, **"Abbrechen"**, und **ausführen** Schaltflächen.  
  
 Öffnen Sie die Headerdatei für die Dialogfeldklasse (in diesem Fall TestProvDlg.h). Fügen Sie der Headerdatei (außerhalb alle Klassendeklarationen) den folgenden Code hinzu:  
  
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
  
 Der Code stellt einen Benutzerdatensatz, der definiert, welche Spalten im Rowset werden. Wenn der Client ruft **IAccessor:: CreateAccessor**, verwendet diese Einträge an, welche Spalten binden. Der OLE DB-Consumervorlagen ermöglichen darüber hinaus für dynamisch gebundene Spalten. Die-Makros handelt es sich um die clientseitige Version der PROVIDER_COLUMN_ENTRY-Makros. Bei den beiden-Makros angeben der Ordnungszahl, Typ, Länge und Datenmember für die beiden Zeichenfolgen.  
  
 Eine Handlerfunktion zum Hinzufügen der **ausführen** Schaltfläche durch Drücken von STRG, und doppelklicken Sie auf die **ausführen** Schaltfläche. Fügen Sie folgenden Code in der Funktion:  
  
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
  
 Die `CCommand`, `CDataSource`, und `CSession` Klassen, die alle an den OLE DB-Consumervorlagen gehören. Jede Klasse wird ein COM-Objekt im Anbieter imitiert. Die `CCommand` -Objekt nimmt die `CProvider` -Klasse, in der Headerdatei als Vorlagenparameter deklariert. Die `CProvider` Parameter darstellt, Bindungen, mit denen Sie Zugriff auf die Daten des Anbieters. So sieht die `Open` Code für die Datenquelle, die Sitzung und den Befehl:  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 Die Zeilen zum Öffnen der einzelnen Klassen erstellen jedes COM-Objekt im Anbieter. Um den Anbieter zu suchen, verwenden Sie die ProgID des Anbieters. Sie erhalten die ProgID aus der Registrierung oder durch einen Blick in die Datei MyProvider.rgs (Directory und suchen Sie nach den Schlüssel ProgID des Anbieters öffnen).  
  
 Die Datei MyData.txt ist im Beispiel MyProv enthalten. Um eine eigene Datei zu erstellen, verwenden Sie einen Editor, und geben Sie eine gerade Anzahl von Zeichenfolgen, die durch Drücken der EINGABETASTE zwischen den einzelnen Zeichenfolgen. Ändern Sie den Pfadnamen aus, wenn Sie die Datei verschieben.  
  
 Übergeben Sie die Zeichenfolge "" c: "\\\samples\\\myprov\\\MyData.txt" in der `table.Open` Zeile. Wenn Sie in Schritt der `Open` aufrufen, sehen Sie, dass diese Zeichenfolge, um übergeben wird die `SetCommandText` Methode im Anbieter. Beachten Sie, dass die `ICommandText::Execute` Methode verwendet diese Zeichenfolge.  
  
 Um die Daten abzurufen, rufen Sie `MoveNext` für die Tabelle. `MoveNext`Ruft die **IRowset:: GetNextRows**, `GetRowCount`, und `GetData` Funktionen. Wenn keine weiteren Zeilen vorhanden sind (d. h. die aktuelle Position im Rowset ist größer als `GetRowCount`), die Schleife beendet:  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 Beachten Sie, dass keine weiteren Zeilen vorhanden sind, Anbieter zurückgeben **DB_S_ENDOFROWSET**. Die **DB_S_ENDOFROWSET** Wert handelt es sich nicht um einen Fehler. Sie sollten immer überprüfen gegen `S_OK` Abbrechen einer Fetch-Schleife von Daten und nicht erfolgreich-Makro verwenden.  
  
 Sie sollten jetzt möglich, erstellen und testen das Programm.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)