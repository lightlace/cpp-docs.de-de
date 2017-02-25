---
title: "Phasen der &#220;bersetzung | Microsoft Docs"
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
helpviewer_keywords: 
  - "Dateiübersetzung [C++], Compilerprozess"
  - "Dateien [C++], Verschiebung"
  - "Präprozessor"
  - "Präprozessor, Verschiebung"
  - "Übersetzungsphasen"
  - "Verschiebung, Compilerprozess"
ms.assetid: a7f7a8c9-e8ba-4321-9e50-ebfbbdcce9db
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Phasen der &#220;bersetzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\- und C\+\+\-Programme bestehen aus mindestens einer Quelldatei, von denen jede einen Teil des Texts des Programms enthält.  Eine Quelldatei wird zusammen mit ihren Includedateien \(Dateien, die mithilfe der Präprozessordirektive `#include` eingeschlossen werden\), aber ohne die Codeabschnitte, die von bedingten Kompilierungsdirektiven entfernt werden, wie beispielsweise `#if`, als "Übersetzungseinheit" bezeichnet.  
  
 Quelldateien können zu unterschiedlichen Zeiten übersetzt werden – tatsächlich werden häufig nur veraltete Dateien übersetzt.  Die übersetzten Übersetzungseinheiten können in separate Objektdateien oder in Objektcodebibliotheken verarbeitet werden.  Diese separaten, übersetzten Übersetzungseinheiten werden anschließend verknüpft, um ein ausführbares Programm oder eine Dynamic Link Library \(DLL\) zu bilden.  Weitere Informationen zu Dateien, die als Eingabe für den Linker verwendet werden können, finden Sie unter [LINK\-Eingabedateien](../build/reference/link-input-files.md).  
  
 Übersetzungseinheiten können mit folgenden Methoden kommunizieren:  
  
-   Aufrufe der Funktionen, die über eine externe Bindung verfügen.  
  
-   Aufrufe der Klassenmemberfunktionen, die über eine externe Bindung verfügen.  
  
-   Direkte Änderung von Objekten, die über eine externe Bindung verfügen.  
  
-   Direkte Änderung von Dateien.  
  
-   Prozessübergreifende Kommunikation \(nur für Microsoft Windows\-basierte Anwendungen\).  
  
 Die folgende Liste beschreibt die Phasen, in denen der Compiler Dateien übersetzt:  
  
 *Zeichenzuordnung*  
 Zeichen in Quelldatei werden zur internen Quelldarstellung zugeordnet.  Trigraphsequenzen werden in dieser Phase in die interne Einzelzeichendarstellung konvertiert.  
  
 *Zusammenführen von Zeilen*  
 Alle Zeilen, die mit einem umgekehrten Schrägstrich \(**\\**\) enden und denen ein Zeilenumbruchzeichen direkt folgt, werden mit der folgenden Zeile in der Quelldatei verknüpft, wodurch logische Zeilen aus den physischen Zeilen gebildet werden.  Falls eine Quelldatei nicht leer ist, muss sie mit einem Zeilenumbruchzeichen enden, dem kein umgekehrter Schrägstrich vorangestellt ist.  
  
 *Zerlegung in Token*  
 Die Quelldatei wird in Vorverarbeitungstoken und Leerstellenzeichen unterteilt.  Kommentare in der Quelldatei werden jeweils durch ein Leerzeichen ersetzt.  Zeilenumbruchzeichen werden beibehalten.  
  
 *Vorverarbeitung*  
 Vorverarbeitungsdirektiven werden ausgeführt, und Makros werden in die Quelldatei erweitert.  Die `#include`\-Anweisung ruft die Übersetzung auf, die mit den vorherigen drei Übersetzungsschritten für jeden enthaltenen Text beginnt.  
  
 *Zeichensatzzuordnung*  
 Alle Quellzeichensatzmember und Escapesequenzen werden in ihre Äquivalente im Ausführungszeichensatz konvertiert.  Für Microsoft C und C\+\+ sind sowohl die Quell\- als auch Ausführungszeichensätze ASCII.  
  
 *Zeichenfolgenverkettung*  
 Alle angrenzenden Zeichenfolgen und breiten Zeichenfolgenliterale werden verkettet.  Beispiel: `"String " "concatenation"` wird zu `"String concatenation"`.  
  
 *Übersetzung*  
 Alle Token werden sowohl syntaktisch als auch semantisch analysiert. Diese Token werden in Objektcode konvertiert.  
  
 *Bindung*  
 Alle externen Verweise werden aufgelöst, um ein ausführbares Programm oder eine Dynamic Link Library zu erstellen.  
  
 Der Compiler gibt während Phasen der Übersetzung, in denen er auf Syntaxfehler trifft, Warnungen oder Fehler aus.  
  
 Der Linker löst alle externen Verweise auf und erstellt ein ausführbares Programm oder eine DLL, indem mindestens eine getrennt verarbeitete Übersetzungseinheit mit Standardbibliotheken kombiniert wird.  
  
## Siehe auch  
 [Präprozessor](../preprocessor/preprocessor.md)