---
title: "CRT-Initialisierung"
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
  - "CRT-Initialisierung [C++]"
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# CRT-Initialisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie CRT globale Zustände im systemeigenen Code initialisiert.  
  
 Standardmäßig enthält der Linker die CRT\-Bibliothek, die den eigenen Startcode bereitstellt.  Dieser Startcode initialisiert die CRT\-Bibliothek, ruft globale Initialisierer auf und ruft dann die vom Benutzer bereitgestellte `main`\-Funktion für Konsolenanwendungen auf.  
  
## Initialisieren eines globalen Objekts  
 Betrachten Sie folgenden Code:  
  
```  
int func(void)  
{  
    return 3;  
}  
  
int gi = func();  
  
int main()  
{  
    return gi;  
}  
```  
  
 Gemäß dem C\/C\+\+\-Standard muss `func()` aufgerufen werden, bevor `main()` ausgeführt wird.  Wer jedoch wird auf?  
  
 Eine Möglichkeit, dies zu bestimmen ist, einen Haltepunkt in `func()` festlegen, die Anwendung debuggen und den Stapel zu überprüfen.  Dies ist möglich, da der CRT\-Quellcode in Visual Studio verfügbar ist.  
  
 Wenn Sie die Funktionen im Stapel wechseln, werden Sie feststellen, dass das CRT durch eine Liste von Funktionszeigern in einer Schleife durchläuft und jedes aufruft, das sie stößt.  Diese Funktionen sind entweder an `func()` oder an Konstruktoren für Klasseninstanzen ähnlich.  
  
 Die CRT\- ruft die Liste von Funktionszeigern vom Visual C\+\+\-Compiler.  Wenn der Compiler einen globalen Initialisierer sieht, generiert er einen dynamischen Initialisierer im Abschnitt `.CRT$XCU` \(wobei `CRT` der Abschnittsname ist und `XCU` der Gruppenname ist\).  Um eine Liste dieser dynamischen Initialisierer abzurufen führen Sie den Befehl **dumpbin \/all main.obj** aus, und suchen Sie anschließend den `.CRT$XCU`\-Abschnitt \(wenn z main.cpp Datei in C\+\+, keine C\-Datei kompiliert wird\).  Es entspricht dem Folgenden:  
  
```  
SECTION HEADER #6  
.CRT$XCU name  
       0 physical address  
       0 virtual address  
       4 size of raw data  
     1F2 file pointer to raw data (000001F2 to 000001F5)  
     1F6 file pointer to relocation table  
       0 file pointer to line numbers  
       1 number of relocations  
       0 number of line numbers  
40300040 flags  
         Initialized Data  
         4 byte align  
         Read Only  
  
RAW DATA #6  
  00000000: 00 00 00 00                                      ....  
  
RELOCATIONS #6  
                                                Symbol    Symbol  
 Offset    Type              Applied To         Index     Name  
 --------  ----------------  -----------------  --------  ------  
 00000000  DIR32                      00000000         C  ??__Egi@@YAXXZ (void __cdecl `dynamic initializer for 'gi''(void))  
```  
  
 Die CRT\- definiert zwei Zeiger:  
  
-   `__xc_a` in `.CRT$XCA`  
  
-   `__xc_z` in `.CRT$XCZ`  
  
 Beide Gruppen verfügen über keine anderen Symbole, außer die `__xc_a` und `__xc_z` definiert werden.  
  
 Wenn verschiedene Gruppen der Linker `.CRT` liest, kombiniert sie in einem Abschnitt und ordnet sie alphabetisch.  Dies bedeutet, dass die benutzerdefinierten globalen Initialisierer \(der Visual C\+\+\-Compiler in `.CRT$XCU` einfügen\), immer nach `.CRT$XCA` und vor `.CRT$XCZ` stammen.  
  
 Der Abschnitt ähnelt dem folgenden:  
  
```  
.CRT$XCA  
            __xc_a  
.CRT$XCU  
            Pointer to Global Initializer 1  
            Pointer to Global Initializer 2  
.CRT$XCZ  
            __xc_z  
```  
  
 Daher verwendet die CRT\-Bibliothek `__xc_a` und `__xc_z`, um den Beginn und das Ende der globalen Initialisiererliste aufgrund der Möglichkeit zu bestimmen, in der sie im Speicher unterschiedlich angeordnet sind, nachdem das Bild geladen wurde.  
  
## Siehe auch  
 [CRT\-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)