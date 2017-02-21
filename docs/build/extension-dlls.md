---
title: "Erweiterungs-DLLs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL-Bibliothek"
  - "DLLs [C++], Erweiterung"
  - "Erweiterungs-DLLs [C++]"
  - "Erweiterungs-DLLs [C++], Informationen über Erweiterungs-DLLs"
  - "Speicher [C++], DLLs"
  - "MFC-DLLs [C++], Erweiterungs-DLLs"
  - "MFC-Erweiterungs-DLLs [C++]"
  - "Gemeinsame Nutzung von Ressourcen [C++]"
  - "Gemeinsam genutzte DLL-Versionen [C++]"
  - "Gemeinsame Ressourcen [C++]"
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erweiterungs-DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine MFC\-Erweiterungs\-DLL ist eine DLL, die typischerweise wiederverwendbare Klassen implementiert, welche von bestehenden Microsoft Foundation Class Library\-Klassen abgeleitet wurden.  
  
 Eine MFC\-Erweiterungs\-DLL hat die folgenden Features und Anforderungen:  
  
-   Die clientseitige ausführbare Datei muss eine MFC\-Anwendung sein, die mit definiertem **\_AFXDLL**\-Symbol kompiliert wurde.  
  
-   Eine Erweiterungs\-DLL kann auch von einer regulären, dynamisch mit MFC verknüpften DLL verwendet werden.  
  
-   Erweiterungs\-DLLs sollten mit definiertem `_AFXEXT`\-Symbol kompiliert werden.  Dadurch wird ebenfalls die Definition von **\_AFXDLL** erzwungen und sichergestellt, dass die korrekten Deklarationen aus den MFC\-Headerdateien übernommen werden.  Zusätzlich wird gewährleistet, dass **AFX\_EXT\_CLASS** beim Erstellen der DLL als **\_\_declspec\(dllexport\)** definiert wird. Das ist erforderlich, wenn Sie dieses Makro zum Deklarieren der Klassen in der Erweiterungs\-DLL verwenden.  
  
-   Erweiterungs\-DLLs sollten keine von `CWinApp` abgeleitete Klasse instanziieren, sondern es vielmehr der Clientanwendung \(bzw. DLL\) überlassen, dieses Objekt bereitzustellen.  
  
-   Erweiterungs\-DLLs sollten jedoch eine `DllMain`\-Funktion bereitstellen und notwendige Initialisierungen dort vornehmen.  
  
 Erweiterungs\-DLLs werden über die Dynamic Link Library\-Version von MFC \(auch als gemeinsam genutzte MFC\-Version bekannt\) erstellt.  Eine Erweiterungs\-DLL kann ausschließlich von ausführbaren MFC\-Dateien \(entweder Anwendungen oder regulären DLLs\) verwendet werden, die mit der gemeinsam genutzten MFC\-Version erstellt wurden.  Sowohl die Clientanwendung als auch die Erweiterungs\-DLL müssen dieselbe Version von MFCx0.dll verwenden.  Mit einer Erweiterungs\-DLL können Sie neue benutzerdefinierte Klassen von MFC ableiten und diese erweiterte MFC\-Version anschließend Anwendungen zur Verfügung stellen, die die DLL aufrufen.  
  
 Erweiterungs\-DLLs können auch dazu verwendet werden, von MFC abgeleitete Objekte zwischen Anwendung und DLL zu übergeben.  Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde.  Da diese Funktionen bei Verwendung der gemeinsam genutzten DLL\-Version von MFC ordnungsgemäß exportiert werden, können problemlos Zeiger auf MFC\-Objekte oder auf von MFC abgeleitete Objekte zwischen einer Anwendung und den von ihr geladenen Erweiterungs\-DLLs übergeben werden.  
  
 Eine MFC\-Erweiterungs\-DLL verwendet die gemeinsam genutzte MFC\-Version auf dieselbe Weise, wie eine Anwendung die gemeinsam genutzte MFC\-DLL\-Version verwendet. Dabei sind jedoch folgende Punkte zu bedenken:  
  
-   Sie verfügt über kein von `CWinApp` abgeleitetes Objekt.  Sie muss mit dem von `CWinApp` abgeleiteten Objekt der Clientanwendung arbeiten.  Das bedeutet, dass sich die Haupt\-Meldungsverteilschleife, die Leerlaufschleife usw. im Besitz der Clientanwendung befinden.  
  
-   Sie ruft `AfxInitExtensionModule` in ihrer `DllMain`\-Funktion auf.  Der Rückgabewert dieser Funktion sollte überprüft werden.  Wird ein NULL\-Wert von `AfxInitExtensionModule` zurückgegeben, muss aus der `DllMain`\-Funktion auch 0 zurückgegeben werden.  
  
-   Während der Initialisierung wird ein **CDynLinkLibrary**\-Objekt erstellt, falls `CRuntimeClass`\-Objekte oder \-Ressourcen von der Erweiterungs\-DLL in die Anwendung exportiert werden sollen.  
  
 Vor MFC, Version 4.0, wurde dieser DLL\-Typ AFXDLL genannt.  Diese Bezeichnung bezieht sich auf das Präprozessorsymbol **\_AFXDLL**, das beim Erstellen der DLL definiert wird.  
  
 Die Importbibliotheken für die gemeinsam genutzte MFC\-Version werden entsprechend der unter [Namenskonventionen für MFC\-DLLs](../build/naming-conventions-for-mfc-dlls.md) beschriebenen Konvention benannt.  Visual C\+\+ bietet vordefinierte Versionen der MFC\-DLLs sowie eine Reihe von MFC\-fremden DLLs, die Sie mit Ihren Anwendungen verwenden und weitergeben können.  Diese sind in der Datei Redist.txt dokumentiert, die im Ordner Programme\\Microsoft Visual Studio installiert ist.  
  
 Wenn Sie den Export über eine DEF\-Datei vornehmen, fügen Sie den folgenden Code am Anfang und am Ende der Headerdatei ein:  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Durch diese vier Zeilen wird sichergestellt, dass der Code ordnungsgemäß für eine Erweiterungs\-DLL kompiliert wird.  Ohne diese vier Zeilen wird die DLL möglicherweise falsch kompiliert oder verknüpft.  
  
 Wenn Sie einen Zeiger auf ein MFC\-Objekt oder auf ein von MFC abgeleitetes Objekt an eine MFC\-DLL übergeben oder aus ihr übernehmen möchten, sollte es sich um eine Erweiterungs\-DLL handeln.  Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde.  Da diese Funktionen bei Verwendung der gemeinsam genutzten DLL\-Version von MFC ordnungsgemäß exportiert werden, können problemlos Zeiger auf MFC\-Objekte oder auf von MFC abgeleitete Objekte zwischen einer Anwendung und den von ihr geladenen Erweiterungs\-DLLs übergeben werden.  
  
 Aufgrund von C\+\+\-spezifischen Problemen bei der Namenscodierung und dem Export kann die Exportliste einer Erweiterungs\-DLL im Debug\- und im Releasebuild derselben DLL bzw. in DLLs für unterschiedliche Plattformen Unterschiede aufweisen.  Das Releasebuild von MFCx0.dll hat ca. 2.000 exportierte Einstiegspunkte, das Debugbuild von MFCx0D.dll ca. 3.000 exportierte Einstiegspunkte.  
  
## Speicherverwaltung  
 MFCx0.dll und alle Erweiterungs\-DLLs, die in den Adressbereich einer Clientanwendung geladen werden, verwenden dieselbe Speicherbelegungsfunktion, dasselbe Ladeverfahren für Ressourcen und weitere globale MFC\-Zustände, so als ob sie in derselben Anwendung enthalten wären.  Dies ist von Bedeutung, da MFC\-fremde DLL\-Bibliotheken und reguläre DLLs genau entgegengesetzt verfahren: Jede DLL belegt Speicher aus ihrem eigenen Bestand.  
  
 Wenn eine Erweiterungs\-DLL Speicher belegt, kann dieser Speicherbereich beliebig mit jedem anderen Objekt, für das die Anwendung Speicher belegt hat, kombiniert werden.  Auch wenn eine dynamisch mit MFC verknüpfte Anwendung nach einer Fehlfunktion beendet wird, bleibt die Integrität anderer MFC\-Anwendungen, die die DLL ebenfalls nutzen, durch die in das Betriebssystem implementierte Schutzfunktion erhalten.  
  
 Entsprechend werden andere globale MFC\-Zustände, wie die aktuelle ausführbare Datei, aus der Ressourcen geladen werden, auch von der Clientanwendung und allen MFC\-Erweiterungs\-DLLs sowie von MFCx0.dll selbst gemeinsam genutzt.  
  
## Gemeinsame Nutzung von Ressourcen und Klassen  
 Der Export von Ressourcen erfolgt über eine Ressourcenliste.  Jede Anwendung enthält eine einfach verknüpfte Liste mit **CDynLinkLibrary**\-Objekten.  Bei den meisten MFC\-Standardimplementierungen, durch die Ressourcen geladen werden, erfolgt die Suche nach einer Ressource zunächst im aktuellen Ressourcenmodul \(`AfxGetResourceHandle`\). Falls diese Suche erfolglos bleibt, wird der Versuch, die angeforderte Ressource zu laden, auf die Liste der **CDynLinkLibrary**\-Objekte ausgeweitet.  
  
 Das Durchlaufen der Liste hat jedoch den Nachteil, dass die Suche etwas langsamer ist und dass die Ressourcen\-ID\-Bereiche verwaltet werden müssen.  Der Vorteil liegt darin, dass eine Clientanwendung, die mit mehreren Erweiterungs\-DLLs verknüpft ist, jede durch die DLL zur Verfügung gestellte Ressource nutzen kann, ohne dass das DLL\-Instanzenhandle angegeben werden muss.  `AfxFindResourceHandle` ist eine API, die bei der Suche nach einer bestimmten Übereinstimmung die Ressourcenliste durchläuft.  Sie verwendet den Ressourcennamen und \-typ als Parameter und gibt das zuerst ermittelte Ressourcenhandle \(oder NULL\) zurück.  
  
 Wenn Sie die Liste nicht durchsuchen und nur Ressourcen von einer bestimmten Stelle laden möchten, verwenden Sie die Funktionen `AfxGetResourceHandle` und `AfxSetResourceHandle`, um das alte Handle zu speichern und das neue Handle festzulegen.  Achten Sie darauf, dass Sie das alte Ressourcenhandle wiederherstellen, bevor Sie zur Clientanwendung zurückkehren.  Ein Beispiel für diese Methode zum expliziten Laden eines Menüs finden Sie in der Datei Testdll2 .cpp im MFC\-Beispiel [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90).  
  
 Die dynamische Erstellung von MFC\-Objekten, die einen MFC\-Namen erhalten, verläuft ähnlich.  Der Mechanismus zur Deserialisierung von MFC\-Objekten erfordert die Registrierung aller `CRuntimeClass`\-Objekte. Auf diese Weise können C\+\+\-Objekte des erforderlichen Typs anhand der zuvor gespeicherten Informationen mittels dynamischer Erstellung rekonstruiert werden.  
  
 Im Fall des MFC\-Beispiels [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90) sieht die Liste etwa folgendermaßen aus:  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
               |                      |  
          TESTDLL2.DLL           TESTDLL2.DLL  
               |                      |  
          TESTDLL1.DLL           TESTDLL1.DLL  
               |                      |  
           MFCOxxD.DLL                |  
               |                      |  
           MFCDxxD.DLL                |  
               |                      |  
            MFCxxD.DLL            MFCxx.DLL  
```  
  
 wobei *xx* die Versionsnummer ist; so steht 42 für die Version 4.2.  
  
 Die MFCxx.dll befindet sich in der Ressourcen\- und Klassenliste gewöhnlich an letzter Stelle.  Die Datei enthält alle MFC\-Standardressourcen, einschließlich der Eingabeaufforderungen aller Standardbefehls\-IDs.  Durch ihre Position am Ende der Liste können DLLs und die Clientanwendung selbst auf die gemeinsam genutzten Ressourcen in MFCxx.dll zugreifen, ohne dass eine eigene Kopie der MFC\-Standardressourcen erforderlich wäre.  
  
 Wenn Sie die Ressourcen und Klassennamen aller DLLs im Namespace der Clientanwendung zusammenführen, hat dies den Nachteil, dass Sie bei der Auswahl von IDs und Namen äußerst sorgfältig vorgehen müssen.  
  
 Im [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90)\-Beispiel wird der Namespace für gemeinsam genutzte Ressourcen mithilfe mehrerer Headerdateien verwaltet.  
  
 Wenn die MFC\-Erweiterungs\-DLL spezielle Daten für jede Anwendung verwalten muss, können Sie eine neue Klasse von **CDynLinkLibrary** ableiten und in `DllMain` erstellen.  Die DLL kann dann bei ihrer Ausführung die Liste der **CDynLinkLibrary**\-Objekte der aktuellen Anwendung überprüfen, um das Objekt für die jeweilige Erweiterungs\-DLL zu suchen.  
  
### Was möchten Sie tun?  
  
-   [Erweiterungs\-DLLs initialisieren](../build/initializing-extension-dlls.md)  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Tips on using shared resource files \(nur auf Englisch verfügbar\)](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [DLL Version of MFC \(nur auf Englisch verfügbar\)](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)