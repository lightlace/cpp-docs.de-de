---
title: Testen des schreibgeschützten Anbieters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4630391d9bce319c35af18767d7133bd34a92362
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990203"
---
# <a name="testing-the-read-only-provider"></a>Testen des schreibgeschützten Anbieters

Um einen Anbieter zu testen, benötigen Sie einen Consumer. Es ist hilfreich, wenn der Consumer mit dem Anbieter vergleichen kann. Die OLE DB-Consumervorlagen sind ein einfacher Wrapper um den OLE DB und mit dem Anbieter-COM-Objekten entsprechen. Da die Quelle der Consumervorlagen ausgeliefert wird, ist es einfach, einen Anbieter mit dem sie debuggen. Die Consumervorlagen sind auch eine sehr klein und schnelle Möglichkeit zum Consumer-Anwendungen zu entwickeln.  
  
Das Beispiel in diesem Thema erstellt eine standardanwendung für MFS-Anwendungsassistenten für einen Testconsumer. Die Anwendung zu testen ist ein einfaches Dialogfeld mit OLE DB-Consumer-Vorlagencode hinzugefügt.  
  
## <a name="to-create-the-test-application"></a>Erstellen Sie die testanwendung  
  
1. Klicken Sie im Menü **Datei** auf **Neu**und dann auf **Projekt**.  
  
1. In der **Projekttypen** wählen Sie im Bereich der **Visual C++-Projekte** Ordner. In der **Vorlagen** wählen Sie im Bereich **MFC-Anwendung**.  
  
1. Geben Sie für den Projektnamen, *TestProv*, und klicken Sie dann auf **OK**.  
  
     Die MFC-Anwendung-Assistent wird angezeigt.  
  
1. Auf der **Anwendungstyp** Seite **auf Dialogfeldern basierend**.  
  
1. Auf der **erweiterte Features** Seite **Automation**, und klicken Sie dann auf **Fertig stellen**.  
  
> [!NOTE]
> Die Anwendung erfordert keine automatisierungsunterstützung aus, wenn Sie hinzufügen, `CoInitialize` in `CTestProvApp::InitInstance`.  
  
Können Sie anzeigen und Bearbeiten der **TestProv** im (IDD_TESTPROV_DIALOG) Wählen sie im Dialogfeld **Ressourcenansicht**. Platzieren Sie zwei Listenfelder, eines für jede Zeichenfolge in das Rowset, das Dialogfeld. Deaktivieren der Sort-Eigenschaft, für beide Felder durch Drücken von Liste **Alt**+**EINGABETASTE** bei ein Listenfeld, das ausgewählt ist, durch Klicken auf die **Stile** Registerkarte und das Löschen der  **Sortierung** Kontrollkästchen. Fügen Sie außerdem eine **ausführen** Schaltfläche im Dialogfeld, um die Datei abzurufen. Die fertige **TestProv** Dialogfeld sollte zwei Listenfelder, die mit der Bezeichnung "String 1" und "String 2", verfügen; es verfügt auch über **OK**, **Abbrechen**, und **ausführen**  Schaltflächen.  
  
Öffnen Sie die Headerdatei für die Dialogfeldklasse (in diesem Fall TestProvDlg.h). Fügen Sie den folgenden Code, der Headerdatei (außerhalb von jedem Klassendeklarationen):  
  
```cpp
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
  
Der Code stellt einen Benutzerdatensatz, der definiert, welche Spalten im Rowset enthalten sein sollen. Wenn der Client ruft `IAccessor::CreateAccessor`, er verwendet diese Einträge aus, um die zu bindenden Spalten anzugeben. Die OLE DB-Consumervorlagen können auch Spalten dynamisch zu binden. Die-Makros handelt es sich um die clientseitige Version der PROVIDER_COLUMN_ENTRY-Makros. Bei den zwei-Makros werden Ordnungszahl Typ, Länge und Datenmember für die beiden Zeichenfolgen.  
  
Hinzufügen eine Handlerfunktion für die **ausführen** Schaltfläche durch Drücken von **STRG** und durch Doppelklicken auf die **ausführen** Schaltfläche. Platzieren Sie den folgenden Code in der Funktion:  
  
```cpp
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider>> table;  
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
  
Die `CCommand`, `CDataSource`, und `CSession` Klassen, die alle zu den OLE DB-Consumervorlagen gehören. Jede Klasse wird ein COM-Objekt im Anbieter imitiert. Die `CCommand` -Objekt nimmt die `CProvider` Klasse, die in der Headerdatei als Vorlagenparameter deklariert. Die `CProvider` Parameter darstellt, Bindungen, die Sie verwenden, um die Daten vom Anbieter zugreifen. Hier ist die `Open` Code für die Datenquelle, Sitzung und -Befehl:  
  
```cpp  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
Die Zeilen zum Öffnen der einzelnen Klassen erstellt jedes COM-Objekt im Anbieter. Verwenden Sie zum Suchen des Anbieters die `ProgID` des Anbieters. Sie erhalten die `ProgID` aus der Registrierung des Systems oder anhand der in der Datei MyProvider.rgs (Öffnen Sie das Verzeichnis des Anbieters, und suchen Sie nach der `ProgID` Schlüssel).  
  
Die Datei "mydata.txt" ist im Lieferumfang der `MyProv` Beispiel. Um eine eigene Datei erstellen, verwenden Sie einen Editor, und geben Sie eine gerade Anzahl von Zeichenfolgen, und Drücken der EINGABETASTE zwischen den einzelnen Zeichenfolgen. Ändern Sie den Pfadnamen aus, wenn Sie die Datei verschieben.  
  
Übergeben Sie die Zeichenfolge "c:\\\samples\\\myprov\\\MyData.txt" in der `table.Open` Zeile. Wenn Sie Sie in Schritt der `Open` Aufruf wird ersichtlich, dass diese Zeichenfolge, um übergeben wird die `SetCommandText` -Methode in der der Anbieter. Beachten Sie, dass die `ICommandText::Execute` Methode verwendet die Zeichenfolge.  
  
Um die Daten abzurufen, rufen Sie `MoveNext` für die Tabelle. `MoveNext` Ruft die `IRowset::GetNextRows`, `GetRowCount`, und `GetData` Funktionen. Wenn keine weiteren Zeilen mehr vorhanden sind (d. h. die aktuelle Position im Rowset ist größer als `GetRowCount`), die Schleife wird beendet:  
  
```cpp  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
Beachten Sie, dass Anbieter DB_S_ENDOFROWSET, wenn keine weiteren Zeilen vorhanden sind zurückgeben, ein. Die DB_S_ENDOFROWSET-Wert ist kein Fehler. Sie sollten immer mit S_OK, um eine Abbrechen und verwenden Sie das Makro SUCCEEDED nicht überprüfen.  
  
Sie sollten jetzt in der Lage zu erstellen und testen das Programm.  
  
## <a name="see-also"></a>Siehe auch  

[Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)