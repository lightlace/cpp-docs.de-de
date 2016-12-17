---
title: "Sicherheitsfunktionen in der CRT"
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
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_CRT_NONSTDC_NO_DEPRECATE"
  - "_CRT_NONSTDC_NO_WARNINGS"
  - "_CRT_SECURE_NO_DEPRECATE"
  - "_CRT_SECURE_NO_WARNINGS"
  - "Pufferüberläufe"
  - "Puffer [C++], Pufferüberläufe"
  - "CRT, Sicherheitserweiterungen"
  - "CRT_NONSTDC_NO_DEPRECATE"
  - "CRT_NONSTDC_NO_WARNINGS"
  - "CRT_SECURE_NO_DEPRECATE"
  - "CRT_SECURE_NO_WARNINGS"
  - "Ablaufwarnung (sicherheitsbezogen)"
  - "Ablaufwarnung (sicherheitsbezogen), Deaktivieren"
  - "Parameter [C++], Überprüfung"
  - "Sicherheit [CRT]"
  - "Sicherheitsablaufwarnung [C++]"
  - "CRT mit erweiterter Sicherheit"
ms.assetid: d9568b08-9514-49cd-b3dc-2454ded195a3
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# Sicherheitsfunktionen in der CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Viele alten CRT\-Funktionen haben die neueren, sichereren Versionen.  Wenn eine sichere Funktion vorhanden ist, wird die ältere, weniger sichere Version, als veraltet gekennzeichnet und die neue Version das Suffix `_s` \("speichern Sie"\), hat.  
  
 In diesem Kontext "veraltete" bedeutet lediglich, dass die Verwendung einer Funktion nicht empfohlen wird; sie zeigt nicht an, dass die Funktion geplant wird, von CRT entfernt werden.  
  
 Die Secure Funktionen nicht verhindert oder korrigieren Sicherheitsfehler; und führen sie Fehler ab, wenn sie auftreten.  Sie übergeben zusätzliche Überprüfungen auf Fehlerzustände aus, und im Falle eines Fehlers, sie rufen einen Fehlerhandler auf \(siehe [Parametervalidierung](../c-runtime-library/parameter-validation.md)\).  
  
 Zum Beispiel verfügt die `strcpy`\-Funktion keine Methode des Mitteilens, wenn die Zeichenfolge, die kopiert, für den Zielpuffer zu groß ist.  Allerdings nimmt seine sicheren Äquivalent, `strcpy_s`, die Größe des Puffers als Parameter deklariert, sodass sie bestimmen, ob ein Pufferüberlauf auftritt.  Wenn Sie `strcpy_s` verwenden, um über elf Zeichen in einen zehn Zeichen Großbuchstaben Puffer zu kopieren, ist der ein Fehler auf dem Teil; `strcpy_s` kann den Fehler nicht korrigieren, aber er kann den Fehler erkannt und informieren Sie, indem den ungültigen Parameterhandler aufruft.  
  
## Ausschließen von Warnmeldungen  
 Es gibt mehrere Methoden, Warnmeldungen für die älteren, weniger sichere Funktionen zu vermeiden.  Das einfachste ist einfach, `_CRT_SECURE_NO_WARNINGS` zu definieren oder das Pragma \- zu verwenden.  Beliebiger deaktiviert Warnmeldungen, jedoch sind natürlich die Sicherheitsprobleme, die die Warnungen noch führen.  Es ist deutlich besser, Warnmeldungen werden aktiviert und die neuen CRT\-Sicherheitsmerkmale zu nutzen.  
  
 In C\+\+ die einfachste Methode auszuführen, die, [Sichere Vorlagenüberladungen](../c-runtime-library/secure-template-overloads.md) zu verwenden, die in vielen Fällen Warnmeldungen beseitigt, indem Aufrufe der veralteten Funktionen mit Aufrufen zu neuen sicheren Versionen dieser Funktionen ersparen.  Betrachten Sie beispielsweise diesen veralteten Aufruf von `strcpy`:  
  
```  
char szBuf[10];   
strcpy(szBuf, "test"); // warning: deprecated   
```  
  
 Das Definieren von `_CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES` als 1 schließt die Warnung, indem Sie den Aufruf `strcpy` in `strcpy_s` ändert, der verhindert Pufferüberläufe.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../c-runtime-library/secure-template-overloads.md).  
  
 Bei veralteten diese Funktionen ohne Speichern Sie Vorlagenüberladungen, sollten Sie den Code, auch manuell aktualisieren bestimmt sollten, die sicheren Versionen verwenden.  
  
 Eine weitere Quelle von Warnmeldungen, keinem Zusammenhang zur Sicherheit, ist die POSIX\-Funktionen.  Ersetzen Sie POSIX\-Funktionsnamen durch ihre Standardentsprechungen, \(z Änderung [Zugriff](../c-runtime-library/reference/access-crt.md) an [\_access](../c-runtime-library/reference/access-waccess.md)\), oder deaktivieren Sie POSIX\-verknüpfte Warnmeldungen, indem Sie `_CRT_NONSTDC_NO_WARNINGS` definieren.  Weitere Informationen finden Sie unter [Deprecated CRT Functions](assetId:///7e259932-c6c8-4c1a-9637-639e591681a5).  
  
## Zusätzliche Sicherheitsfeatures  
 Einige der Sicherheitsfeatures gehören folgende:  
  
-   `Parameter Validation`.  Parameter haben von CRT\-Funktionen werden überprüft, in beiden Funktionen speichern und in vielen Versionen von bereits vorhandenen Funktionen.  Diese Validierungen:  
  
    -   Das Überprüfen der `NULL`\-Werte an Funktionen.  
  
    -   Überprüfungsenumerationswerte Gültigkeit.  
  
    -   Das Überprüfen dieses ganzzahlige Werte sind in den gültigen Bereichen.  
  
-   Weitere Informationen finden Sie unter [Parametervalidierung](../c-runtime-library/parameter-validation.md).  
  
-   Ein Handler für ungültige Parameter ist auch für Entwickler zugänglich.  Wenn eine vor derartigen eines ungültigen Parameters, anstatt, die Anwendung erläutern und zu beenden, CRT, eine Methode stellt zu überprüfen, arbeiten diese Probleme mit [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md).  
  
-   `Sized Buffers`.  Die Secure Funktionen erfordern, dass die Puffergröße an eine Funktion übergeben, die auf einen Puffer schreibt.  Die sicheren Versionen überprüfen, ob der Puffer groß genug ist, bevor er darauf schreibt und hilft, gefährliche Pufferüberlauffehler zu vermeiden, die bösartigen Code schützen ermöglichen können, das die Ausführung.  Diese Funktionen geben normalerweise einem `errno` Fehlertypcode zurück und rufen den ungültigen Parameterhandler auf, wenn die Größe des Puffers zu klein ist.  Funktionen, die von den Eingabepuffern, wie `gets` Lese\-, sichere Versionen haben, die Sie benötigen, einer maximalen Größe anzugeben.  
  
-   `Null termination`.  Einige Funktionen, die möglicherweise nicht\-beendete Zeichenfolgen haben, sichere Versionen haben, die sicherstellen, dass sich die Zeichenfolgen ordnungsgemäß beendet ungültiges sind.  
  
-   `Enhanced error reporting`.  Die Rückholfehlercodes der sicheren Funktionen mit weiteren Fehlerinformationen, als verfügbar mit den bereits vorhandenen Funktionen war.  Die Funktionen sicheren und viele der bereits vorhandene Funktionen jetzt sowohl `errno` und geben häufig einen Codetyp auch `errno` zurück, um einen einwandfreien Fehlerbericht bereitzustellen.  
  
-   `Filesystem security`.  Sichere Datei\-E\/A APIstützsicherer Dateizugriff im Standardfall.  
  
-   `Windows security`.  Sichere Prozessapis erzwingen Sicherheitsrichtlinien und ermöglichen die Angabe von ACLs.  
  
-   `Format string syntax checking`.  Ungültige Zeichenfolgen werden beispielsweise mit der falschen Typfeldzeichen in Formatzeichenfolgen  `printf` erkannt.  
  
## Siehe auch  
 [Parametervalidierung](../c-runtime-library/parameter-validation.md)   
 [Sichere Vorlagenüberladungen](../c-runtime-library/secure-template-overloads.md)   
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)