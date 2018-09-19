---
title: CRT-Initialisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRT initialization [C++]
ms.assetid: e7979813-1856-4848-9639-f29c86b74ad7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 965955cf5c92ba627227292d513c9b2bda57cd48
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031919"
---
# <a name="crt-initialization"></a>CRT-Initialisierung

In diesem Thema wird beschrieben, wie CRT globale Status in nativem Code initialisiert.

Standardmäßig enthält der Linker die CRT-Bibliothek, die einen eigenen Startcode bereitstellt. Dieser Startcode initialisiert die CRT-Bibliothek, ruft globale Initialisierer auf und ruft dann die vom Benutzer bereitgestellte `main`-Funktion für Konsolenanwendungen auf.

## <a name="initializing-a-global-object"></a>Initialisieren eines globalen Objekts

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

Laut dem C/C++-Standard muss `func()` aufgerufen werden, bevor `main()` ausgeführt wird. Doch wer ruft diese Funktion auf?

Eine Möglichkeit für die Beantwortung dieser Frage besteht darin, einen Haltepunkt in `func()` festzulegen, die Anwendung zu debuggen und den Stapel zu überprüfen. Dies ist möglich, da der CRT-Quellcode in Visual Studio enthalten ist.

Wenn Sie die Funktionen im Stapel durchsuchen, werden Sie feststellen, dass CRT eine Liste der Funktionszeiger durchläuft und dabei jeden Einzelnen aufruft. Diese Funktionen ähneln entweder `func()` oder Konstruktoren für Klasseninstanzen.

CRT ruft die Liste der Funktionszeiger aus dem Visual C++-Compiler ab. Wenn der Compiler einen globalen Initialisierer erkennt, generiert er einen dynamischen Initialisierer im Abschnitt `.CRT$XCU` (wobei `CRT` für den Namen des Abschnitts und `XCU` für den Gruppennamen steht). Um eine Liste dieser dynamischen Initialisierer abzurufen, führen Sie den Befehl **dumpbin/all main.obj** aus, und durchsuchen Sie dann den Abschnitt `.CRT$XCU` (sofern „main.cpp“ als C++-Datei und nicht als C-Datei kompiliert ist). Sie sieht ungefähr wie folgt aus:

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

CRT definiert zwei Zeiger:

- `__xc_a` in `.CRT$XCA`

- `__xc_z` in `.CRT$XCZ`

Bei beiden Gruppen sind keine Symbole definiert, außer `__xc_a` und `__xc_z`.

Wenn der Linker verschiedene `.CRT`-Gruppen liest, fasst er sie in einem Bereich zusammen und sortiert sie in alphabetischer Reihenfolge. Dies bedeutet, dass die benutzerdefinierten globalen Initialisierer (die der Visual C++-Compiler in `.CRT$XCU` einfügt) immer nach `.CRT$XCA` und vor `.CRT$XCZ` kommen.

Der Abschnitt ähnelt der folgenden Ausgabe:

```
.CRT$XCA
            __xc_a
.CRT$XCU
            Pointer to Global Initializer 1
            Pointer to Global Initializer 2
.CRT$XCZ
            __xc_z
```

Deshalb verwendet die CRT-Bibliothek `__xc_a` und `__xc_z`, um den Anfang und das Ende der Liste der globalen Initialisierer zu ermitteln. Grund hierfür ist die Art und Weise, wie sie im Arbeitsspeicher angeordnet werden, nachdem das Image geladen wurde.

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)