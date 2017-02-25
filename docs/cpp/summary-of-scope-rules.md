---
title: "Zusammenfassung der Bereichsregeln | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassennamen [C++], Bereichsregeln"
  - "Klassenbereich [C++], Regeln"
  - "Klassen [C++], Gültigkeitsbereich"
  - "Namen [C++], Klasse"
  - "Bereich [C++], Klassennamen"
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Zusammenfassung der Bereichsregeln
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Verwendung eines Name muss innerhalb seines Bereichs eindeutig sein \(bis zu dem Punkt, an dem das Überladen bestimmt wird\).  Wenn der Name eine Funktion kennzeichnet, muss die Funktion im Hinblick auf Anzahl und Typ der Parameter eindeutig sein.  Wenn der Name eindeutig bleibt, werden [Memberzugriff](../cpp/member-access-control-cpp.md)\-Regeln angewendet.  
  
## Konstruktorinitialisierer  
 Die Konstruktorinitialisierer \(siehe unter [Initialisieren von Basen und Membern](assetId:///2f71377e-2b6b-49da-9a26-18e9b40226a1)\) werden im Gültigkeitsbereich des äußersten Blocks des Konstruktors ausgewertet, für den sie angegeben werden.  Daher können sie die Parameternamen des Konstruktors verwenden.  
  
## Globale Namen  
 Ein Name eines Objekts, einer Funktion oder eines Enumerators ist global, wenn er außerhalb einer Funktion oder Klasse eingefügt oder ihm der globale unäre Bereichsoperator \(`::`\) vorangestellt wird und er nicht in Verbindung mit einem dieser binären Operatoren verwendet wird:  
  
-   Bereichsauflösung \(`::`\)  
  
-   Memberauswahl für Objekte und Verweise \(**.**\)  
  
-   Memberauswahl für Zeiger \(**–\>**\)  
  
## Qualifizierte Namen  
 Namen, die mit dem binären Bereichsauflösungsoperator \(`::`\) verwendet werden, werden als "qualifizierte Namen" bezeichnet. Der Name, der nach dem binären Bereichsauflösungsoperator angegeben wird, muss einem Member der Klasse entsprechen, der auf der linken Seite des Operators angegeben oder ein Member der Basisklasse\(n\) ist.  
  
 Namen, die nach dem Memberauswahloperator \(**.** oder **–\>**\) angegeben werden, müssen Member des Klassentyps des Objekts sein, das auf der linken Seite des Operators oder Members seiner Basisklasse angegeben wird.  Namen, die rechts vom Memberauswahloperator \(**–\>**\) angegeben werden, können auch Objekte eines anderen Klassentyps sein, sofern die linke Seite von **–\>** ein Klassenobjekt ist und die Klasse einen überladenen Memberauswahloperator \(**–\>**\) definiert, der zu einem Zeiger auf einen anderen Klassentyp ausgewertet wird.  \(Diese Bereitstellung wird unter [Klassenmemberzugriff](../cpp/member-access.md) ausführlicher erläutert.\)  
  
 Der Compiler sucht nach Namen in der folgenden Reihenfolge und hört auf, wenn der Name gefunden wird:  
  
1.  Aktueller Blockgültigkeitsbereich, wenn der Name innerhalb einer Funktion verwendet wird; andernfalls globaler Gültigkeitsbereich.  
  
2.  Nach außen durch jeden einschließenden Blockbereich, einschließlich des äußersten Gültigkeitsbereichs der Funktion \(der Funktionsparameter enthält\).  
  
3.  Wenn der Name innerhalb einer Memberfunktion verwendet wird, wird der Gültigkeitsbereich der Klasse nach dem Namen durchsucht.  
  
4.  Die Basisklassen der Klasse werden nach dem Namen durchsucht.  
  
5.  Der einschließende, verschachtelte Klassenbereich \(sofern vorhanden\) und seine Basen werden durchsucht.  Die Suche wird fortgesetzt, bis der äußerste einschließende Klassenbereich durchsucht wurde.  
  
6.  Globaler Gültigkeitsbereich wird durchsucht.  
  
 Sie können jedoch wie folgt Änderungen an dieser Suchreihenfolge vornehmen:  
  
1.  Namen, denen `::` vorangestellt wird, zwingen die Suche, im globalen Gültigkeitsbereich zu starten.  
  
2.  Namen, denen die Schlüsselwörter **class**, `struct` und **union** vorangestellt sind, zwingen den Compiler, nur nach den Namen **class**, `struct` oder **union** zu suchen.  
  
3.  Namen auf der linken Seite des Bereichsauflösungsoperators \(`::`\) können nur die Namen **class**, `struct`, **namespace** oder **union** aufweisen.  
  
 Wenn der Name auf einen nicht statischen Member verweist, aber in einer statischen Memberfunktion verwendet wird, wird eine Fehlermeldung generiert.  Und wenn der Name auf einen nicht statischen Member in einer einschließenden Klasse verweist, wird eine Fehlermeldung generiert, da eingeschlossene Klassen keinen **this**\-Zeiger für einschließende Klassen besitzen.  
  
## Funktionsparameternamen  
 Funktionsparameternamen in Funktionsdefinitionen werden als Bestandteil des Gültigkeitsbereichs des äußersten Blocks der Funktion angesehen.  Daher sind sie lokale Namen und verlassen den Gültigkeitsbereich, wenn die Funktion beendet wird.  
  
 Funktionsparameternamen in Funktionsdeklarationen \(Prototypen\) befinden sich im lokalen Gültigkeitsbereich der Deklaration und verlassen den Gültigkeitsbereich am Ende der Deklaration.  
  
 Standardparameter befinden sich im Gültigkeitsbereich des Parameters, für das sie die Standardeinstellung sind, wie in den beiden vorherigen Absätzen beschrieben.  Sie können jedoch nicht auf lokale Variablen oder nicht statische Klassenmember zugreifen.  Standardparameter werden zum Zeitpunkt des Funktionsaufrufs, aber im ursprünglichen Gültigkeitsbereich der Funktionsdeklaration ausgewertet.  Deshalb werden die Standardparameter für Memberfunktionen immer im Klassengültigkeitsbereich ausgewertet.  
  
## Siehe auch  
 [Vererbung](../cpp/inheritance-cpp.md)