---
title: "&lt;filesystem&gt;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "filesystem/std::tr2::sys::directory_entry"
  - "filesystem/std::tr2::sys::recursive_directory_iterator"
  - "filesystem/std::tr2::sys::path"
  - "filesystem/std::tr2::sys::filesystem_error"
  - "filesystem/std::tr2::sys::directory_iterator"
  - "<filesystem>"
dev_langs: 
  - "C++"
ms.assetid: 5005753b-46fa-43e1-8d4e-1b38617d3cfd
caps.latest.revision: 27
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# &lt;filesystem&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beziehen Sie den Header \<filesystem\> für den Zugriff auf Klassen und Funktion mit ein, die Informationen über Pfade, Dateien und Verzeichnisse ändern und abrufen.  
  
## Syntax  
  
```cpp  
#include <filesystem>  
using namespace std::tr2::sys;  
```  
  
> [!IMPORTANT]
>  Ab C\+\+ 14 handelt es sich beim \<filesystem\>\-Header noch nicht um einen C\+\+\-Standard. Es wird jedoch erwartet, dass er in etwa in seiner aktuellen Form im C\+\+ 17\-Zeitfenster standardisiert wird.  
  
 Dieser Header unterstützt Dateisysteme für eine von zwei umfangreichen Klassen von Hostbetriebssystemen: Microsoft Windows und POSIX.  
  
 Der überwiegende Teil der Funktionalität ist für beide Betriebssysteme gleich. In diesem Dokuments sind die Unterschiede aufgeführt. Zum Beispiel:  
  
-   Windows unterstützt mehrere Stammnamen, etwa „c:“ oder „\\\\Netzwerkname“. Daher besteht ein Dateisystem aus einer Gesamtstruktur von Strukturen, von denen jede ein eigenes Stammverzeichnis, z. B. „c:\\“ oder „\\\\Netzwerkname\\“, und ein eigenes aktuelles Verzeichnis hat, um einen relativen Pfadnamen \(ein Pfadname, der kein absoluter Pfadnamen ist\) zu komplettieren.  
  
-   POSIX unterstützt eine einzige Struktur, ohne Stammnamen, das einzige Stammverzeichnis \/ und ein einziges aktuelles Verzeichnis.  
  
 Ein weiterer wichtiger Unterschied ist die systemeigene Darstellung von Pfadnamen:  
  
-   Windows verwendet eine nullterminierte Sequenz von wchar\_t\-Zeichen, die als UTF\-16 codiert sind \(ein oder zwei Elemente für jedes Zeichen\).  
  
-   POSIX verwendet eine nullterminierte von char\-Zeichen, die als UTF\-8 codiert sind \(ein oder mehrere Elemente für jedes Zeichen\).  
  
-   Ein Objekt eines Klassenpfads speichert den Pfadnamen im systemeigenen Format, unterstützt aber einfache Konvertierung zwischen dieser gespeicherten Form und mehreren externen Formen:  
  
    -   Eine nullterminierte Sequenz von char\-Zeichen, die entsprechend der Vorgabe des Betriebssystems codiert sind  
  
    -   Eine nullterminierte Sequenz von char\-Zeichen, die als UTF\-8 codiert sind  
  
    -   Eine nullterminierte Sequenz von wchar\_t\-Zeichen, die entsprechend der Vorgabe des Betriebssystems codiert sind  
  
    -   Eine nullterminierte Sequenz von char16\_t\-Zeichen, die als UTF\-16 codiert sind  
  
    -   Eine nullterminierte Sequenz von char32\_t\-Zeichen, die als UTF\-32 codiert sind  
  
 Gegenseitige Konvertierungen zwischen diesen Darstellungen werden nach Bedarf dadurch vermittelt, dass mindestens ein codecvt\-Facet verwendet wird. Wenn ein bestimmtes Gebietsschemaobjekt nicht festgelegt ist, werden dieser Facets aus dem globalen Gebietsschema abgerufen.  
  
 Ein weiterer Unterschied ist das Detail, über das das jeweilige Betriebssystem Ihnen die Möglichkeit gibt, Datei\- oder Verzeichniszugriffsberechtigungen anzugeben:  
  
1.  Windows protokolliert, ob eine Datei schreibgeschützt ist oder schreibbar ist. Dies ist ein Attribut, das für Verzeichnisse keine Bedeutung hat.  
  
2.  POSIX protokolliert, ob eine Datei vom Besitzer, von der Gruppe des Besitzers oder von jedem gelesen , geschrieben oder ausgeführt \(durchsucht, wenn Verzeichnis\) werden kann, und protokolliert einige andere Berechtigungen.  
  
 Beiden Systemen gemeinsam ist die Struktur, die für einen Pfadnamen gilt, sobald Sie über den Stammnamen hinausgelangen. Für den Pathnamen „c:\/abc\/xyz\/def.ext“ gilt:  
  
-   Der Stammname ist „c:“.  
  
-   Das Stammverzeichnis ist \/.  
  
-   Der Stammpfad ist „c:\/“.  
  
-   Der relative Pfad ist „abc\/xyz\/def.ext“.  
  
-   Der übergeordnete Pfad ist „c:\/abc\/xyz“.  
  
-   Der Dateiname ist „def.ext“.  
  
-   Der Stamm ist „def“.  
  
-   Die Erweiterung ist „.ext“.  
  
 Ein geringfügiger Unterschied ist das **bevorzugte Trennzeichen**, das zwischen der Sequenz von Verzeichnissen in einem Pfadnamen verwendet wird. In beiden Betriebssysteme können Sie einen Schrägstrich \(\/\) schreiben, aber in bestimmten Kontexten bevorzugt Windows einen umgekehrten Schrägstrich \(\\\).  
  
 Ein wichtiges Feature von Pfadobjekten ist schließlich, dass Sie diese überall dort verwenden können, wo ein Argument namens „filename“ in den Klassen erforderlich ist, die im Header \<fstream\> definiert sind.  
  
 Weitere Informationen und Codebeispiele finden Sie unter [Dateisystemnavigation \(C\+\+\)](../standard-library/file-system-navigation.md).  
  
## Klassen  
  
|Name|Beschreibung|  
|----------|------------------|  
|directory\_entry\-Klasse|Beschreibt ein Objekt, das durch einen „directory\_iterator“ oder einen „recursive\_directory\_iterator“ zurückgegeben wird, und es enthält Informationen über eine|  
|directory\_iterator\-Klasse.|Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Dateisystemverzeichnis durchläuft.|  
|filesystem\_error\-Klasse|Eine Basisklasse für Ausnahmen, die ausgelöst werden, um einen Systemüberlauf auf niedriger Ebene zu melden.|  
|path\-Klasse|Definiert eine Klasse, die ein für die Verwendung als Dateiname geeignetes Objekt des Vorlagentyps `String` speichert.|  
|recursive\_directory\_iterator\-Klasse|Beschreibt einen Eingabeiterator, der alle Dateinamen in einem Dateisystemverzeichnis durchläuft. Der Iterator kann die Verzeichnisse auch absteigend anordnen.|  
|[file\_status\-Klasse](../standard-library/file-status-class.md)|Bricht ein `file_type` um.|  
  
## Strukturen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[space\_info\-Struktur](../standard-library/space-info-structure.md)|Enthält Informationen zu einem Volume.|  
  
## Funktionen  
 [\<filesystem\>\-Funktionen](../standard-library/filesystem-functions.md)  
  
## Operatoren  
 [\<filesystem\>\-Operatoren](../standard-library/filesystem-operators.md)  
  
## Enumerationen  
  
|Name|Beschreibung|  
|----------|------------------|  
|[copy\_option\-Enumeration](../Topic/copy_option%20Enumeration%20%3Cfilesystem%3E.md)|Eine mit [copy\_file](assetId:///4af7a9b0-8861-45ed-b84e-0307f0669d60) verwendete Enumeration, mit der das Verhalten bestimmt wird, wenn eine Datei vorhanden ist.|  
|[directory\_options\-Enumeration](../Topic/directory_options%20Enumeration.md)|Eine Enumeration, die Optionen für Verzeichnisiteratoren angibt.|  
|[file\_type\-Enumeration](../Topic/file_type%20Enumeration.md)|Eine Enumeration für Dateitypen.|  
|[perms\-Enumeration](../Topic/perms%20Enumeration.md)|Ein Bitmaskentyp, mit dem Berechtigungen und Optionen zu Berechtigungen übermittelt werden.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)