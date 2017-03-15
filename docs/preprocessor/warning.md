---
title: "warning | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "warning_CPP"
  - "vc-pragma.warning"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop warning-Pragma"
  - "Pragmas, warning"
  - "push pragma warning"
  - "warning-Pragma"
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# warning
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aktiviert die selektive Änderung des Verhaltens der Compilerwarnmeldungen.  
  
## Syntax  
  
```  
  
      #pragma warning(   
      warning-specifier  
       :   
      warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## Hinweise  
 Die folgenden Parameter für Warnungsbezeichner stehen zur Verfügung.  
  
|warning\-specifier|Bedeutung|  
|------------------------|---------------|  
|`1, 2, 3, 4`|Wenden Sie die angegebene Ebene auf die angegebenen Warnung\(en\) an.  Dadurch aktiviert sich auch eine angegebene Warnung, die standardmäßig deaktiviert ist.|  
|`default`|Setzen Sie das Warnverhalten auf den Standardwert zurück.  Dadurch aktiviert sich auch eine angegebene Warnung, die standardmäßig deaktiviert ist.  Die Warnung wird auf der standardmäßigen dokumentierten Ebene generiert.<br /><br /> Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|`disable`|Geben Sie die angegebene\(n\) Warnung\(en\) nicht aus.|  
|`error`|Melden Sie die angegebenen Warnungen als Fehler.|  
|`once`|Zeigen Sie die angegebene\(n\) Meldung\(en\) nur einmal an.|  
|`suppress`|Schiebt den aktuellen Zustand des Pragmas auf den Stapel, deaktiviert die angegebene Warnung für die nächste Zeile und ruft dann den Warnungsstapel auf, sodass der Pragmazustand zurückgesetzt wird.|  
  
 Die folgende Codeanweisung veranschaulicht, dass ein Parameter `warning-number-list` mehrere Warnungsnummern enthalten kann und dass mehrere Parameter `warning-specifier` in der gleichen Pragmadirektive angegeben werden können.  
  
```  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 Dies entspricht hinsichtlich der Funktion dem folgenden Code.  
  
```  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 Der Compiler fügt 4000 zu jeder Warnungsnummer zwischen 0 und 999 hinzu.  
  
 Bei Warnungszahlen im Bereich 4700–4999, die mit der Codegenerierung zusammenhängen, wird der Status der Warnung aktiviert, wenn der Compiler auf die geöffnete geschweifte Klammer einer Funktion stößt, und er bleibt für den Rest der Funktion aktiv.  Das Verwenden des `warning`\-Pragmas in der Funktion zum Ändern des Zustands einer Warnung, die eine Zahl größer als 4699 aufweist, tritt erst nach dem Ende der Funktion in Kraft.  Das folgende Beispiel zeigt die korrekte Platzierung des Pragmas `warning` zur Deaktivierung einer Codegenerierungs\-Warnmeldung und zur anschließenden Wiederherstellung.  
  
```  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 Beachten Sie, dass im gesamten Funktionstext die letzte Einstellung des `warning`\-Pragmas für die gesamte Funktion gelten wird.  
  
## Push und Pop  
 Das Pragma `warning` unterstützt auch die nachstehende Syntax.  
  
 `#pragma warning(` `push` \[ `,``n` \] `)`  
  
 `#pragma warning(` `pop )`  
  
 Dabei stellt `n` eine Warnstufe dar \(1 bis 4\).  
  
 Das Pragma `warning( push )` speichert den aktuellen Warnzustand für jede Warnung.  Das Pragma `warning( push,` `n``)` speichert den aktuellen Zustand für jede Warnung und legt die globale Warnstufe auf `n` fest.  
  
 Das Pragma `warning( pop )` ruft den letzten Warnzustand auf, der auf den Stapel übertragen wurde.  Alle Änderungen, die Sie zwischen `push` und `pop` am Warnzustand vorgenommen haben, werden rückgängig gemacht.  Betrachten Sie das folgende Beispiel:  
  
```  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 Am Ende dieses Codes, stellt `pop` den Zustand jeder Warnung wieder her \(einschließlich 4705, 4706 und 4707\), der zu Beginn des Codes vorlag.  
  
 Wenn Sie Headerdateien schreiben, können Sie `push` und `pop` verwenden, um sicherzustellen, dass Änderungen des Warnzustands, die von einem Benutzer vorgenommen wurden, nicht verhindern, dass der Header ordnungsgemäß kompiliert wird.  Verwenden Sie `push` am Anfang des Headers und `pop` am Ende.  Wenn Sie beispielsweise über einen Header verfügen, der nicht ordnungsgemäß auf Warnstufe 4 kompiliert, würde der folgende Code die Warnstufe auf 3 ändern und anschließend die ursprüngliche Warnstufe am Ende des Headers wiederherstellen.  
  
```  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 Weitere Informationen zu Compileroptionen, die Ihnen helfen, Warnungen zu unterdrücken, finden Sie unter [\/FI](../build/reference/fi-name-forced-include-file.md) und [\/w](../build/reference/compiler-option-warning-level.md).  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)