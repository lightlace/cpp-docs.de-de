---
title: "Dateisystemnavigation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f7cc5f5e-a541-4e00-87c7-a3769ef6096d
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Dateisystemnavigation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Header \<filesystem\> implementiert den Entwurf der technischen Dateisystemspezifikation \([ISO\/IEC JTC 1\/SC 22\/WG 21 N4100](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n4100.pdf)\) und enthält Typen und Funktionen, mit denen Sie plattformunabhängigen Code für die Navigation im Dateisystem schreiben können. Da er plattformübergreifend ist, enthält er APIs, die für Windows\-Systeme nicht relevant sind. Dies bedeutet beispielsweise, dass `is_fifo(const path&)` unter Windows immer `false` zurückgibt. Der Header basiert auf dem Entwurf einer technischen Spezifikation, die nicht in den C\+\+17\-Standard von Visual Studio 2015 RTM gewählt wurde. Seine Elemente befinden sich im `std::experimental::filesystem::v1`\-Namespace.  
  
## Übersicht  
 Verwenden Sie die \<filesystem\>\-APIs für die folgenden Aufgaben:  
  
-   Durchlaufen von Dateien und Verzeichnissen unter einem angegebenen Pfad  
  
-   Abrufen von Informationen zu Dateien, einschließlich Erstellungszeitpunkt, Größe, Erweiterung und Stammverzeichnis  
  
-   Erstellen, Zerlegen und Vergleichen von Pfaden  
  
-   Erstellen, Kopieren und Löschen von Verzeichnissen  
  
-   Kopieren und Löschen von Dateien  
  
 Weitere Informationen zu Datei\-E\/A mit der Standardbibliothek finden Sie unter [iostream\-Programmierung](../standard-library/iostream-programming.md).  
  
## Pfade  
  
### Erstellen und Zerlegen von Pfaden  
 In Windows \(ab XP\) werden Pfade systemintern in Unicode gespeichert. Die [Pfad](../standard-library/path-class-cpp-standard-template-library.md)klasse führt automatisch alle erforderlichen Zeichenfolgenkonvertierungen durch. Sie akzeptiert Argumente von Arrays von breiten und schmalen Zeichen sowie `std::string`\- und `std::wstring`\-Typen im UTF8\- oder UTF16\-Format. Mit der `path`\-Klasse werden Pfadtrennzeichen automatisch normalisiert. Sie können einen einzelnen Schrägstrich als Verzeichnistrennzeichen in Konstruktorargumenten verwenden. Dadurch können Sie die gleichen Zeichenfolgen zum Speichern von Pfaden in Windows\- und UNIX\-Umgebungen verwenden:  
  
```cpp  
path pathToDisplay(L"/FileSystemTest/SubDir3"); // OK! path pathToDisplay2(L"\\FileSystemTest\\SubDir3"); // Still OK as always path pathToDisplay3(LR"(\FileSystemTest\SubDir3)"); // Raw string literals are OK, too.  
```  
  
 Zum Verketten zweier Pfade können Sie überladene  `/`\- und `/=`\-Operatoren verwenden, die analog zu den `+`\- und `+=`\-Operatoren in `std::string` und `std::wstring` sind. Das `path`\-Objekt stellt Trennzeichen bereit, wenn Sie dies nicht tun.  
  
```cpp  
path myRoot("C:/FileSystemTest"); // no trailing separator, no problem! myRoot /= path("SubDirRoot"); // C:/FileSystemTest/SubDirRoot  
```  
  
### Überprüfen von Pfaden  
 Die Pfadklasse verfügt über mehrere Methoden, mit denen Informationen über die verschiedenen Pfadteile zurückgegeben werden, im Unterschied zur Dateisystementität, auf die sie verweisen können. Sie können den Stamm, relativen Pfad, Dateinamen, die Dateierweiterung usw. abrufen. Sie können Pfadobjekte durchlaufen, um alle Ordner in der Hierarchie zu überprüfen. Das folgende Beispiel veranschaulicht, wie ein Pfad durchlaufen werden kann \(nicht das Verzeichnis, auf das er verweist\)und Informationen zu den Pfadteilen abgerufen werden können.  
  
```cpp  
  
#include <string> #include <iostream> #include <sstream> #include <filesystem> using namespace std; using namespace std::experimental::filesystem::v1; wstring  DisplayPathInfo() { // This path may or may not refer to an existing file. We are // examining this path string, not file system objects. path pathToDisplay(L"C:/FileSystemTest/SubDir3/SubDirLevel2/File2.txt "); wostringstream wos; int i = 0; wos << L"Displaying path info for: " << pathToDisplay << endl; for (path::iterator itr = pathToDisplay.begin(); itr != pathToDisplay.end(); ++itr) { wos << L"path part: " << i++ << L" = " << *itr << endl; } wos << L"root_name() = " << pathToDisplay.root_name() << endl << L"root_path() = " << pathToDisplay.root_path() << endl << L"relative_path() = " << pathToDisplay.relative_path() << endl << L"parent_path() = " << pathToDisplay.parent_path() << endl << L"filename() = " << pathToDisplay.filename() << endl << L"stem() = " << pathToDisplay.stem() << endl << L"extension() = " << pathToDisplay.extension() << endl; return wos.str(); } void main(int argc, char* argv[]) { wcout << DisplayPathInfo() << endl; // wcout << ComparePaths() << endl; // see following example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
 Durch den Code wird die folgende Ausgabe generiert:  
  
```cpp  
Displaying path info for: C:\FileSystemTest\SubDir3\SubDirLevel2\File2.txt path part: 0 = C: path part: 1 = \ path part: 2 = FileSystemTest path part: 3 = SubDir3 path part: 4 = SubDirLevel2 path part: 5 = File2.txt root_name() = C: root_path() = C:\ relative_path() = FileSystemTest\SubDir3\SubDirLevel2\File2.txt parent_path() = C:\FileSystemTest\SubDir3\SubDirLevel2 filename() = File2.txt stem() = File2 extension() = .txt  
```  
  
### Vergleichen von Pfaden  
 Die `path`\-Klasse überlädt die gleichen Vergleichsoperatoren wie `std::string` und `std::wstring`. Beim Vergleichen von zwei Pfaden führen Sie einen Zeichenfolgenvergleich durch, nachdem die Trennzeichen normalisiert wurden. Wenn ein nachstehender Schrägstrich \(oder umgekehrter Schrägstrich\) fehlt, wird dieser nicht hinzugefügt und wirkt sich auf den Vergleich aus. Im folgenden Beispiel wird der Vergleich von Pfadwerten veranschaulicht:  
  
```cpp  
  
wstring ComparePaths() { path p0(L"C:/Documents"); // no trailing separator path p1(L"C:/Documents/"); //p0 < p1 path p2(L"C:/Documents/2013/"); // p1 < p2 path p3(L"C:/Documents/2013/Reports/"); // p2 < p3 path p4(L"C:/Documents/2014/");  // p3 < p4 path p5(L"D:/Documents/2013/Reports/"); // p4 < p5 wostringstream wos; wos << boolalpha << p0.wstring() << L" < " << p1.wstring() << L": " << (p0 < p1) << endl << p1.wstring() << L" < " << p2.wstring() << L": " << (p1 < p2) << endl << p2.wstring() << L" < " << p3.wstring() << L": " << (p2 < p3) << endl << p3.wstring() << L" < " << p4.wstring() << L": " << (p3 < p4) << endl << p4.wstring() << L" < " << p5.wstring() << L": " << (p4 < p5) << endl; return wos.str(); } /* Output: C:\Documents < C:\Documents\: true C:\Documents\ < C:\Documents\2013\: true C:\Documents\2013\ < C:\Documents\2013\Reports\: true C:\Documents\2013\Reports\ < C:\Documents\2014\: true C:\Documents\2014\ < D:\Documents\2013\Reports\: true */  
```  
  
 Um diesen Code auszuführen, fügen Sie ihn in das vollständige Beispiel oben ein, und heben Sie in main die Auskommentierung der Zeile auf, die ihn aufruft.  
  
### Konvertieren zwischen Pfad\- und Zeichenfolgentypen  
 Ein `path`\-Objekt ist implizit in `std::wstring` oder `std::string` konvertibel. Dies bedeutet, Sie können einen Pfad an Funktionen wie [wofstream::open](../Topic/basic_ofstream::open.md), wie im folgenden Beispiel dargestellt, übergeben.  
  
```cpp  
wchar_t* p = L"C:/test"; path filePath(p); filePath /= L"NewFile.txt"; // Open, write to, and close the file. wofstream myFile; myFile.open(filePath); myFile << L"Lorem ipsum..."; myFile.close  
  
```  
  
## Durchlaufen von Verzeichnissen und Dateien  
 Der \<filesystem\>\-Header stellt den [directory\_iterator](../standard-library/directory-iterator-class.md)\-Typ zum Durchlaufen der einzelnen Verzeichnisse und die [recursive\_directory\_iterator](../standard-library/recursive-directory-iterator-class.md)\-Klasse zum rekursiven Durchlaufen eines Verzeichnisses und seiner Unterverzeichnisse bereit. Wenn Sie einen Iterator erstellt haben, indem Sie ihm ein `path`\-Objekt übergeben haben, verweist der Iterator auf den ersten „directory\_entry“ im Pfad. Erstellen Sie den End\-Iterator, indem Sie den Standardkonstruktor aufrufen.  
  
 Beim Durchlaufen eines Verzeichnisses können verschiedene Arten von Elementen auftreten, u. a. Verzeichnisse, Dateien, symbolische Verknüpfungen und Socketdateien. Der `directory_iterator` gibt seine Elemente als [directory\_entry](../standard-library/directory-entry-class.md)\-Objekte zurück, wobei jedes Element über ein [status\(\)](assetId:///a70a3c55-3a76-417f-abaf-862ff94b2056)\-Element verfügt, das Auskunft über die Art des angezeigten Eintrag gibt. Mithilfe dieses Werts können Sie Entscheidungen zur Vorgehensweise für einen bestimmten Eintrag treffen. Im folgenden Beispiel werden ein einzelnes Verzeichnis durchlaufen, und, wenn der Verzeichniseintrag eine reguläre Datei ist, Informationen zur Datei vom Code ausgegeben. Wenn der Eintrag ein Verzeichnis ist, wird nur der Name angezeigt.  
  
```cpp  
#include <string> #include <iostream> #include <iomanip> #include <filesystem> #include <chrono> #include <time.h> using namespace std; using namespace std::experimental::filesystem::v1; // Display the last write time for the file wstring LastWriteTimeToLocalTime(const path& file_path) { const auto last = chrono::system_clock::to_time_t(last_write_time(file_path)); tm timeinfo; localtime_s(&timeinfo, &last); wchar_t buf[56]; _wasctime_s(buf, 56, &timeinfo); // appends '\n' return wstring{ buf }; } // List files and directories in the specified path void DisplayFolderContents(const path& p) { wcout << L"Begin iterating " << p.wstring() << endl; for (const auto& entry : directory_iterator{ p }) { if (is_regular_file(entry.status())) { wcout << L" File: " << entry.path().filename() << " : " << LastWriteTimeToLocalTime(entry.path()); } else if (is_directory(entry.status())) { wcout << L" Dir: " << entry.path().filename() << endl; } } } void main() { wstring dir{ LR"(C:\users\public\documents\)" }; path p{ dir }; if (!is_directory(p)) { wcout << L"No such directory: " << dir << endl; return; } DisplayFolderContents(p); // IterateFolderRecursively(p); // see example wcout << endl << L"Press Enter to exit" << endl; wstring input; getline(wcin, input); }  
```  
  
### Rekursives Durchlaufen einer Verzeichnisstruktur  
 Das folgende Beispiel zeigt, wie eine Verzeichnisstruktur rekursiv durchlaufen werden kann. Um diese Funktion auszuführen, fügen Sie sie in das vorherige Codebeispiel hinter der Funktion „DisplayFolderContents“ ein, und heben Sie in main die Auskommentierung der Zeile auf, die ihn aufruft.  
  
```cpp  
// List files and directories recursively in the path void IterateFolderRecursively(const path& p) { wcout << L"Begin iterating " << p.wstring() << " recursively" << endl; for (recursive_directory_iterator it{ p }, end; it != end; ++it) { if (is_regular_file(it->status())) { wcout << setw(it.depth()) << L" " << L"File: " << it->path().filename() << L" : " << LastWriteTimeToLocalTime(it->path()); } else if (is_directory(it->status())) { wcout << setw(it.depth()) << L" " << L"Dir: " << it->path().filename() << endl; } } }  
```  
  
### Behandeln symbolischer Verknüpfungen  
 Die Erkennung von symbolischen Verknüpfungen wird in Visual C\+\+ ab Visual Studio 2015 nicht unterstützt.