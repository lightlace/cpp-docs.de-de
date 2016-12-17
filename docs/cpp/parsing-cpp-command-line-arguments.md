---
title: "Analysieren von C++-Befehlszeilenargumenten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anführungszeichen, Befehlszeilenargumente"
  - "Doppelte Anführungszeichen"
  - "Analysieren der Befehlszeile"
  - "Analysieren, Befehlszeilen-Argumente"
  - "Startcode, Analysieren von Befehlszeilenargumenten"
ms.assetid: e634e733-ac2f-4298-abe2-7e9288c94951
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Analysieren von C++-Befehlszeilenargumenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft-spezifisch**  
  
 Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der Microsoft C/C++-Startcode die folgenden Regeln:  
  
-   Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.  
  
-   Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem vollständig verarbeitet, bevor es an das `argv`-Array im Programm übergeben wird.  
  
-   Eine in doppelte Anführungszeichen eingeschlossene Zeichenfolge ("*Zeichenfolge*") wird als einzelnes Argument enthaltenen Leerräume interpretiert. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.  
  
-   Ein doppeltes Anführungszeichen ein umgekehrter Schrägstrich vorangestellt (\\") wird als ein Zeichen literales Anführungszeichen (") interpretiert.  
  
-   Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.  
  
-   Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das doppelte Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.  
  
-   Wenn auf eine ungerade Anzahl umgekehrter Schrägstriche ein doppeltes Anführungszeichen folgt, wird für jedes Paar von umgekehrten Schrägstrichen ein umgekehrter Schrägstrich in das `argv`-Array eingefügt, und das doppelte Anführungszeichen wird vom verbleibenden umgekehrten Schrägstrich mit einem Escapezeichen versehen, sodass ein echtes doppeltes Anführungszeichen (") in `argv` eingefügt wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Programm zeigt, wie Befehlszeilenargumente übergeben werden:  
  
```  
// command_line_arguments.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
int main( int argc,      // Number of strings in array argv  
          char *argv[],   // Array of command-line argument strings  
          char *envp[] )  // Array of environment variable strings  
{  
    int count;  
  
    // Display each command-line argument.  
    cout << "\nCommand-line arguments:\n";  
    for( count = 0; count < argc; count++ )  
         cout << "  argv[" << count << "]   "  
                << argv[count] << "\n";  
}  
```  
  
 Die folgende Tabelle zeigt beispielhafte Eingaben und zu erwartende Ausgaben, wobei die Regeln in der vorangehenden Liste aufgezeigt werden.  
  
### <a name="results-of-parsing-command-lines"></a>Ergebnisse der Analyse von Befehlszeilen  
  
|Befehlszeileneingabe|argv[1]|Argv [2]|Argv [3]|  
|-------------------------|---------------|---------------|---------------|  
|`"abc" d e`|`abc`|`d`|`e`|  
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|  
|`a\\\"b c d`|`a\"b`|`c`|`d`|  
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|  
  
## <a name="end-microsoft-specific"></a>Ende Microsoft-spezifisch  
  
## <a name="see-also"></a>Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)