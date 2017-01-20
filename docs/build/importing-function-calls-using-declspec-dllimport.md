---
title: "Importieren von Funktionsaufrufen mithilfe von &quot;__declspec(dllimport)&quot;"
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
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport)-Schlüsselwort [C++]"
  - "dllimport-Attribut [C++], Funktionsaufrufimporte"
  - "Funktionsaufrufe [C++], Importieren"
  - "Importieren von Funktionsaufrufen [C++]"
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Importieren von Funktionsaufrufen mithilfe von &quot;__declspec(dllimport)&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das folgende Codebeispiel veranschaulicht die Verwendung von **\_declspec\(dllimport\)** zum Importieren von Funktionsaufrufen aus einer DLL in eine Anwendung.  Angenommen, die Funktion `func1` befindet sich in einer DLL, die nicht mit der EXE\-Datei, in der die **main**\-Funktion enthalten ist, verbunden ist.  
  
 Der folgende Code zeigt die Verwendung ohne **\_\_declspec\(dllimport\)**:  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 In diesem Fall generiert der Compiler mit dem folgenden Beispiel vergleichbaren Code:  
  
```  
call func1  
```  
  
 Der Linker übersetzt den Aufruf in etwa wie folgt:  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 Wenn `func1` in einer weiteren DLL enthalten ist, ist keine direkte Auflösung möglich, da der Linker die Adresse von `func1` nicht ermitteln kann.  In 16\-Bit\-Umgebungen fügt der Linker diese Codeadresse einer Liste in der EXE\-Datei hinzu, die das Ladeprogramm dann zur Laufzeit mit der richtigen Adresse überschreibt.  In 32\-Bit\- und 64\-Bit\-Umgebungen generiert der Linker einen Thunk, dessen Adresse ihm bekannt ist.  In einer 32\-Bit\-Umgebung sieht der Thunk folgendermaßen aus:  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 Hier ist `imp_func1` die Adresse für den Slot von `func1` in der Importadressentabelle der EXE\-Datei.  Folglich sind dem Linker alle Adressen bekannt.  Das Ladeprogramm muss nur die Importadressentabelle der EXE\-Datei zur Ladezeit aktualisieren, damit alles richtig funktioniert.  
  
 Die Verwendung von **\_\_declspec\(dllimport\)** ist ratsam, da der Linker keinen Thunk generiert, wenn es nicht erforderlich ist.  Durch Thunks wird der Code umfangreicher \(auf RISC\-Systemen kann dies mehrere Anweisungen umfassen\), und die Cacheleistung wird u. U. beeinträchtigt.  Wenn Sie dem Compiler mitteilen, dass sich die Funktion in einer DLL befindet, kann dieser einen indirekten Aufruf generieren.  
  
 Daher wird durch folgenden Code:  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 diese Anweisung generiert:  
  
```  
call DWORD PTR __imp_func1  
```  
  
 Da es keinen Thunk und keine `jmp`\-Anweisung gibt, ist der Code weniger umfangreich und schneller ausführbar.  
  
 Andererseits möchten Sie für Funktionsaufrufe innerhalb einer DLL keinen indirekten Aufruf verwenden.  Sie kennen bereits die Adresse einer Funktion,  und da es Zeit und Speicherplatz kostet, die Funktionsadresse vor einem indirekten Aufruf zu laden und speichern, ist ein direkter Aufruf stets kleiner und schneller.  **\_\_declspec\(dllimport\)** ist nur dann erforderlich, wenn DLL\-Funktionen außerhalb der DLL selbst aufgerufen werden.  Beim Erstellen dieser DLL sollte **\_\_declspec\(dllimport\)** nicht für Funktionen innerhalb einer DLL verwendet werden.  
  
## Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)