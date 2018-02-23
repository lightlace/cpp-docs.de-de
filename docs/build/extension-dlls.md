---
title: Erweiterungs-DLLs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxdll
dev_langs:
- C++
helpviewer_keywords:
- memory [C++], DLLs
- MFC extension DLLs [C++]
- AFXDLL library
- shared resources [C++]
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- resource sharing [C++]
- extension DLLs [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: f69ac3d4-e474-4b1c-87a1-6738843a135c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36a57d47d32b4526ca6d383b67ca415f705dc982
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2018
---
# <a name="mfc-extension-dlls"></a>MFC-Erweiterungs-DLLs
Eine MFC-Erweiterungs-DLL ist eine DLL, die typischerweise wiederverwendbare Klassen implementiert, welche von bestehenden Microsoft Foundation Class Library-Klassen abgeleitet wurden.  
  
 Eine MFC-Erweiterungs-DLL hat die folgenden Funktionen und Anforderungen:  
  
-   Der ausführbare Client muss eine MFC-Anwendung mit kompiliert `_AFXDLL` definiert.  
  
-   Eine MFC-Erweiterungs-DLL kann auch von einer regulären MFC-DLL verwendet werden, die dynamisch mit MFC verknüpft wird.  
  
-   MFC-Erweiterungs-DLLs kompiliert werden soll, mit `_AFXEXT` definiert. Dies zwingt `_AFXDLL` definiert werden und sichergestellt, dass die korrekten Deklarationen aus den MFC-Headerdateien per Pull abgerufen wird. Zusätzlich wird gewährleistet, die `AFX_EXT_CLASS` ist definiert als `__declspec(dllexport)` beim Erstellen der DLL, dies ist erforderlich, wenn Sie dieses Makro zum Deklarieren der Klassen in der MFC-Erweiterungs-DLL verwenden.  
  
-   MFC-Erweiterungs-DLLs sollten nicht instanziieren eine Klasse abgeleitet `CWinApp`, jedoch sollten, hängen davon ab, die Clientanwendung (bzw. DLL), dieses Objekt bereitzustellen.  
  
-   MFC-Erweiterungs-DLLs sollten, bieten jedoch eine `DllMain` -Funktion und die erforderlichen Initialisierungen dort vornehmen.  
  
 Erweiterungs-DLLs werden über die Dynamic Link Library-Version von MFC (auch als gemeinsam genutzte MFC-Version bekannt) erstellt. Nur ausführbaren MFC-Dateien (entweder Anwendungen oder regulären MFC-DLLs), die mit der gemeinsam genutzten MFC-Version erstellt wurden, können eine MFC-Erweiterungs-DLL verwenden. Die Clientanwendung und die MFC-Erweiterungs-DLL müssen dieselbe Version von MFCx0.dll verwenden. Mit dem eine MFC-Erweiterungs-DLL können Sie neue benutzerdefinierte Klassen von MFC ableiten und dann bieten diese erweiterte MFC-Version für Anwendungen, die die DLL aufrufen.  
  
 Erweiterungs-DLLs können auch dazu verwendet werden, von MFC abgeleitete Objekte zwischen Anwendung und DLL zu übergeben. Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde. Da diese Funktionen bei Verwendung die gemeinsam genutzten DLL-Version von MFC ordnungsgemäß exportiert werden, können Sie kostenlos MFC übergeben oder Zeiger von MFC abgeleitete Objekte zwischen einer Anwendung und den MFC-Erweiterungs-DLLs geladen.  
  
 Eine MFC-Erweiterungs-DLL verwendet die gemeinsam genutzte MFC-Version auf dieselbe Weise, wie eine Anwendung die gemeinsam genutzte MFC-DLL-Version verwendet. Dabei sind jedoch folgende Punkte zu bedenken:  
  
-   Sie verfügt über kein von `CWinApp` abgeleitetes Objekt. Sie muss mit dem von `CWinApp` abgeleiteten Objekt der Clientanwendung arbeiten. Das bedeutet, dass sich die Haupt-Meldungsverteilschleife, die Leerlaufschleife usw. im Besitz der Clientanwendung befinden.  
  
-   Sie ruft `AfxInitExtensionModule` in ihrer `DllMain`-Funktion auf. Der Rückgabewert dieser Funktion sollte überprüft werden. Wird ein NULL-Wert von `AfxInitExtensionModule` zurückgegeben, muss aus der `DllMain`-Funktion auch 0 zurückgegeben werden.  
  
-   Erstellt eine **CDynLinkLibrary** -Objekt während der Initialisierung, wenn die MFC-Erweiterungs-DLL exportiert werden sollen `CRuntimeClass` Objekte oder-Ressourcen von der Anwendung.  
  
 Vor MFC, Version 4.0, wurde dieser DLL-Typ AFXDLL genannt. Diese Bezeichnung bezieht sich auf die `_AFXDLL` Präprozessorsymbol, das beim Erstellen der DLL definiert ist.  
  
 Die Importbibliotheken für die gemeinsam genutzte MFC-Version werden gemäß der Konvention, die in beschriebenen benannt [Namenskonventionen für MFC-DLLs](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Visual C++ bietet vordefinierte Versionen der MFC-DLLs sowie eine Reihe von MFC-fremden DLLs, die Sie mit Ihren Anwendungen verwenden und weitergeben können. Diese sind in der Datei Redist.txt dokumentiert, die im Ordner Programme\Microsoft Visual Studio installiert ist.  
  
 Wenn Sie den Export über eine DEF-Datei vornehmen, fügen Sie den folgenden Code am Anfang und am Ende der Headerdatei ein:  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Diese vier Zeilen wird sichergestellt, dass der Code ordnungsgemäß für eine MFC-Erweiterungs-DLL kompiliert wird. Ohne diese vier Zeilen wird die DLL möglicherweise falsch kompiliert oder verknüpft.  
  
 Wenn eine MFC übergeben werden müssen oder MFC abgeleitete Objektzeiger zu oder von einer MFC-DLL, die DLL eine MFC-Erweiterungs-DLL muss. Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde. Da diese Funktionen bei Verwendung die gemeinsam genutzten DLL-Version von MFC ordnungsgemäß exportiert werden, können Sie kostenlos MFC übergeben oder Zeiger von MFC abgeleitete Objekte zwischen einer Anwendung und den MFC-Erweiterungs-DLLs geladen.  
  
 Aufgrund von C++ Name-mangling und Export von Problemen kann die Exportliste einer MFC-Erweiterungs-DLL die Debug- und im Versionen derselben DLL bzw. in DLLs für unterschiedliche Plattformen aufweisen. Das Releasebuild von MFCx0.dll hat ca. 2.000 exportierte Einstiegspunkte, das Debugbuild von MFCx0D.dll ca. 3.000 exportierte Einstiegspunkte.  
  
## <a name="memory-management"></a>Speicherverwaltung  
 MFCx0.dll und alle MFC-Erweiterungs-DLLs in den Adressbereich einer Clientanwendung geladen verwenden dieselbe Speicherbelegungsfunktion, Ladeverfahren für Ressourcen und weitere globale MFC-Zustände als wären sie in der gleichen Anwendung. Dies ist wichtig, da die MFC - fremde DLL-Bibliotheken und reguläre MFC-DLLs genau entgegengesetzt Verfahren und jede DLL belegt Speicher aus ihrem eigenen Bestand.  
  
 Wenn eine MFC-Erweiterungs-DLL Speicher belegt wird, kann diesen Arbeitsspeicher frei mit jedem anderen Anwendung zugeordnete Objekt mischen. Auch wenn eine dynamisch mit MFC verknüpfte Anwendung nach einer Fehlfunktion beendet wird, bleibt die Integrität anderer MFC-Anwendungen, die die DLL ebenfalls nutzen, durch die in das Betriebssystem implementierte Schutzfunktion erhalten.  
  
 Entsprechend werden andere globale MFC-Zustände, wie die aktuelle ausführbare Datei, aus der Ressourcen geladen werden, auch von der Clientanwendung und allen MFC-Erweiterungs-DLLs sowie von MFCx0.dll selbst gemeinsam genutzt.  
  
## <a name="sharing-resources-and-classes"></a>Gemeinsame Nutzung von Ressourcen und Klassen  
 Der Export von Ressourcen erfolgt über eine Ressourcenliste. Jede Anwendung enthält eine einfach verknüpfte Liste mit **CDynLinkLibrary** Objekte. Wenn Sie für eine Ressource zu suchen, suchen die meisten MFC-standardimplementierungen, die Ressourcen geladen werden zunächst im aktuellen Ressourcenmodul (`AfxGetResourceHandle`) und wenn die Ressource nicht gefunden wird, führen Sie die Liste der **CDynLinkLibrary** Objekte Es wird versucht, auf die angeforderte Ressource zu laden.  
  
 Das Durchlaufen der Liste hat jedoch den Nachteil, dass die Suche etwas langsamer ist und dass die Ressourcen-ID-Bereiche verwaltet werden müssen. Es hat den Vorteil, dass eine Clientanwendung, die mit mehreren MFC-Erweiterungs-DLLs verknüpft jede DLL bereitgestellten Ressource verwenden kann, ohne die DLL-Instanzenhandle angegeben. `AfxFindResourceHandle` ist eine API, die bei der Suche nach einer bestimmten Übereinstimmung die Ressourcenliste durchläuft. Sie verwendet den Ressourcennamen und -typ als Parameter und gibt das zuerst ermittelte Ressourcenhandle (oder NULL) zurück.  
  
 Wenn Sie die Liste nicht durchsuchen und nur Ressourcen von einer bestimmten Stelle laden möchten, verwenden Sie die Funktionen `AfxGetResourceHandle` und `AfxSetResourceHandle`, um das alte Handle zu speichern und das neue Handle festzulegen. Achten Sie darauf, dass Sie das alte Ressourcenhandle wiederherstellen, bevor Sie zur Clientanwendung zurückkehren. Ein Beispiel für diese Methode zum expliziten Laden eines Menüs finden Sie in der Datei Testdll2 .cpp im MFC-Beispiel [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk).  
  
 Die dynamische Erstellung von MFC-Objekten, die einen MFC-Namen erhalten, verläuft ähnlich. Der Mechanismus zur Deserialisierung von MFC-Objekten erfordert die Registrierung aller `CRuntimeClass`-Objekte. Auf diese Weise können C++-Objekte des erforderlichen Typs anhand der zuvor gespeicherten Informationen mittels dynamischer Erstellung rekonstruiert werden.  
  
 Im Fall des MFC-Beispiels [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk), die Liste sieht ungefähr so aus:  
  
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
  
 wobei *Xx* ist die Versionsnummer; z. B. steht 42 für die Version 4.2.  
  
 Die MFCxx.dll befindet sich in der Ressourcen- und Klassenliste gewöhnlich an letzter Stelle. Die Datei enthält alle MFC-Standardressourcen, einschließlich der Eingabeaufforderungen aller Standardbefehls-IDs. Durch ihre Position am Ende der Liste können DLLs und die Clientanwendung selbst auf die gemeinsam genutzten Ressourcen in MFCxx.dll zugreifen, ohne dass eine eigene Kopie der MFC-Standardressourcen erforderlich wäre.  
  
 Wenn Sie die Ressourcen und Klassennamen aller DLLs im Namespace der Clientanwendung zusammenführen, hat dies den Nachteil, dass Sie bei der Auswahl von IDs und Namen äußerst sorgfältig vorgehen müssen.  
  
 Die [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) Beispiel Namespace freigegebene Ressource mithilfe mehrerer Headerdateien verwaltet.  
  
 Wenn die MFC-Erweiterungs-DLL spezielle Daten für jede Anwendung verwalten muss, leiten Sie eine neue Klasse von **CDynLinkLibrary** und erstellen Sie ihn in `DllMain`. Beim Ausführen, kann die DLL Überprüfen der aktuellen Anwendung Liste **CDynLinkLibrary** -Objekten, die das Objekt für die jeweilige MFC-Erweiterungs-DLL zu suchen.  
  
### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [MFC-Erweiterungs-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Tipps zur Verwendung der gemeinsam genutzte Ressourcendateien](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
  
-   [DLL Version of MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)