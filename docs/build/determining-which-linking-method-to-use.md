---
title: "Bestimmen der geeigneten Verkn&#252;pfungsmethode"
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
  - "Explizite Verknüpfung [C++]"
  - "Implizite Verknüpfung [C++]"
ms.assetid: 6b6d3fec-4711-4a30-af5b-354b965ecaec
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Bestimmen der geeigneten Verkn&#252;pfungsmethode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es stehen zwei Typen von Verknüpfungen zur Verfügung: implizites Verknüpfen und explizites Verknüpfen.  
  
## Implizite Verknüpfung  
 Die [implizite Verknüpfung](../build/linking-implicitly.md) findet statt, wenn der Code einer Anwendung eine exportierte DLL\-Funktion aufruft.  Beim Kompilieren oder Assemblieren des Quellcodes für die aufrufende ausführbare Datei wird durch den DLL\-Funktionsaufruf ein Verweis auf eine externe Funktion im Objektcode generiert.  Um diesen externen Verweis aufzulösen, muss die Anwendung mit der Importbibliothek \(LIB\-Datei\) verknüpft werden, die vom Ersteller der DLL bereitgestellt wird.  
  
 Die Importbibliothek enthält nur Code zum Laden der DLL sowie zum Implementieren von Funktionsaufrufen in der DLL.  Wenn in einer Importbibliothek eine externe Funktion gefunden wird, wird der Linker informiert, dass der Code für diese Funktion in einer DLL enthalten ist.  Um externe Verweise auf DLLs aufzulösen, fügt der Linker der ausführbaren Datei einfach Informationen hinzu. Dadurch wird dem System mitgeteilt, wo der DLL\-Code zu finden ist, wenn der Prozess startet.  
  
 Wenn vom System ein Programm gestartet wird, das dynamisch verknüpfte Verweise enthält, verwendet es die Informationen in der ausführbaren Programmdatei, um die benötigten DLLs zu finden.  Wird die DLL nicht gefunden, beendet das System den Prozess und zeigt ein Dialogfeld mit einer entsprechenden Fehlermeldung an.  Andernfalls ordnet das System die DLL\-Module im Adressbereich des Prozesses zu.  
  
 Wenn eine der DLLs über eine Einstiegspunktfunktion \(mit Initialisierungs\- und Terminierungscode\) verfügt, ruft das Betriebssystem die Funktion auf.  Über einen der Parameter, die an die Einstiegspunktfunktion übergeben werden, wird Code definiert, der angibt, dass die DLL an den Prozess angefügt wird.  Wenn die Einstiegspunktfunktion nicht den Wert **TRUE** zurückgibt, beendet das System den Prozess mit einer entsprechenden Fehlermeldung.  
  
 Schließlich ändert das System den ausführbaren Code des Prozesses, um Startadressen für die DLL\-Funktionen bereitzustellen.  
  
 Der DLL\-Code wird, wie der übrige Programmcode, nach dem Prozessstart im Adressbereich des Prozesses zugeordnet. Er wird nur bei Bedarf in den Arbeitsspeicher geladen.  Somit haben die von DEF\-Dateien früherer Windows\-Versionen verwendeten Codeattribute **PRELOAD** und **LOADONCALL**, durch die das Laden gesteuert wurde, ihre Bedeutung verloren.  
  
## Explizite Verknüpfung  
 Die meisten Anwendungen verwenden die implizite Verknüpfung, da diese Verknüpfungsmethode am einfachsten anzuwenden ist.  Es gibt jedoch Situationen, in denen die [explizite Verknüpfung](../build/linking-explicitly.md) erforderlich ist.  Die folgenden Gründe sprechen häufig für die explizite Verknüpfung:  
  
-   Die Anwendung kennt den Namen der DLL nicht, die bis zur Laufzeit geladen werden muss.  Es ist z. B. möglich, dass die Anwendung den Namen der DLL und der exportierten Funktionen aus einer Konfigurationsdatei abrufen muss.  
  
-   Ein Prozess, der die implizite Verknüpfung verwendet, wird vom Betriebssystem beendet, wenn die DLL beim Starten des Prozesses nicht gefunden wird.  Verwendet ein Prozess die explizite Verknüpfung, wird er in dieser Situation nicht beendet und kann versuchen, die Verarbeitung fortzusetzen.  So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.  
  
-   Ein Prozess, der die implizite Verknüpfung verwendet, wird auch beendet, wenn eine der DLLs, mit denen er verknüpft ist, eine fehlgeschlagene `DllMain`\-Funktion enthält.  Verwendet ein Prozess die explizite Verknüpfung, wird er in dieser Situation nicht beendet.  
  
-   Eine Anwendung, die implizit mit zahlreichen DLLs verknüpft ist, wird u. U. langsam gestartet, da von Windows neben der Anwendung auch alle DLLs geladen werden.  Um den Start zu beschleunigen, kann eine Anwendung zunächst implizit mit denjenigen DLLs verknüpft werden, die direkt nach dem Laden benötigt werden, während die explizite Verknüpfung mit den anderen DLLs erst erfolgt, wenn diese benötigt werden.  
  
-   Durch die explizite Verknüpfung entfällt die Notwendigkeit, die Anwendung mit einer Importbibliothek zu verknüpfen.  Wenn sich die Exportordinalzahlen aufgrund von Änderungen in der DLL ändern, müssen Anwendungen, die die explizite Verknüpfung verwenden, nicht erneut verknüpft werden \(vorausgesetzt, sie rufen **GetProcAddress** über einen Funktionsnamen und nicht über einen Ordinalwert auf\). Anwendungen, die die implizite Verknüpfung verwenden, müssen jedoch erneut mit der neuen Importbibliothek verknüpft werden.  
  
 Beachten Sie die beiden folgenden Schwachstellen im Zusammenhang mit der expliziten Verknüpfung:  
  
-   Wenn die DLL eine `DllMain`\-Funktion als Einstiegspunkt hat, ruft das Betriebssystem die Funktion im Kontext des Threads auf, der **LoadLibrary** aufgerufen hat.  Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist, da es einen früheren Aufruf von **LoadLibrary** ohne entsprechenden Aufruf der **FreeLibrary**\-Funktion gegeben hat.  Die explizite Verknüpfung kann Probleme verursachen, wenn die DLL die Initialisierung der einzelnen Prozessthreads über eine `DllMain`\-Funktion ausführt. Dies liegt daran, dass die beim Aufrufen von **LoadLibrary** \(oder `AfxLoadLibrary`\) bereits vorhandenen Threads nicht initialisiert werden.  
  
-   Wenn eine DLL statische Daten als **\_\_declspec\(thread\)** deklariert, kann dies zu einer Schutzverletzung führen, sobald explizit verknüpft wird.  Nachdem die DLL mit **LoadLibrary** geladen wurde, verursacht sie eine Schutzverletzung, sobald vom Code auf diese Daten verwiesen wird. \(Statische Daten umfassen sowohl globale als auch lokale statische Elemente.\) Daher sollten Sie beim Erstellen einer DLL entweder die lokale Threadspeicherung vermeiden oder die DLL\-Benutzer über die möglichen Gefahren informieren \(die beim dynamischen Laden auftreten können\).  
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Explizite Verknüpfungen verwenden](../build/linking-explicitly.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   ["LoadLibrary" und "AfxLoadLibrary"](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   ["FreeLibrary" und "AfxFreeLibrary"](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [\<caps:sentence id\="tgt47" sentenceid\="8081a197f9413cac12a30b57c2612af5" class\="tgtSentence"\>Using thread local storage in a dynamic\-link library \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms686997)  
  
## Siehe auch  
 [Verknüpfen einer ausführbaren Datei mit einer DLL](../build/linking-an-executable-to-a-dll.md)