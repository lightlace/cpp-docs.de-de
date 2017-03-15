---
title: "Linkertoolwarnung LNK4049 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4049"
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Linkertoolwarnung LNK4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lokal definiertes Symbol "Symbol" wurde importiert  
  
 Das Symbol wurde sowohl aus dem Programm exportiert als auch in das Programm importiert.  
  
 Diese Warnung wird vom Linker generiert, wenn Sie ein Symbol mit dem `__declspec(dllexport)`\-Speicherklassenattribut in einer Objektdatei deklarieren und mit dem `__declspec(dllimport)`\-Attribut in einer anderen Objektdatei darauf verweisen.  
  
 Warnung LNK4049 ist eine allgemeinere Version von [Linkertoolwarnung LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md).  Der Linker generiert die Warnung LNK4049, wenn nicht bestimmt werden kann, von welcher Funktion auf das importierte Symbol verwiesen wurde.  
  
 Häufig wird LNK4049 in folgenden Fällen statt LNK4217 generiert:  
  
-   Inkrementelles Verknüpfen mit der Option [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md)  
  
-   Optimierung des ganzen Programms mit der Option [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md)  
  
 Führen Sie einen der folgenden Schritte aus, um die Warnung LNK4049 zu vermeiden:  
  
-   Entfernen Sie die `__declspec(dllimport)`\-Namensdeklaration aus der Vorwärtsdeklaration des Symbols, das LNK4049 ausgelöst hat.  Sie können nach Symbolen in einem Binärdateiabbild suchen, indem Sie das Dienstprogramm **DUMPBIN** verwenden.  Der **DUMPBIN\/SYMBOLS**\-Schalter zeigt die COFF\-Symboltabelle des Abbilds an.  Weitere Informationen zum Dienstprogramm **DUMPBIN** finden Sie unter [DUMPBIN\-Referenz](../../build/reference/dumpbin-reference.md).  
  
-   Deaktivieren Sie das inkrementelle Verknüpfen und die Optimierung des ganzen Programms vorübergehend.  Bei einer Neukompilierung der Anwendung wird die Warnung LNK4217 generiert, die den Namen der Funktion enthält, von der auf das importierte Symbol verwiesen wurde.  Entfernen Sie die `__declspec(dllimport)`\-Deklaration aus dem importierten Symbol, und aktivieren Sie je nach Bedarf das inkrementelle Verknüpfen oder die Optimierung des ganzen Programms.  
  
 Der letztendlich generierte Code verhält sich zwar richtig, der Code zum Aufrufen der importierten Funktion ist jedoch weniger effizient als ein direkter Aufruf der Funktion.  Diese Warnung wird nicht angezeigt, wenn Sie zum Kompilieren die Option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) verwenden  
  
 Weitere Informationen zum Importieren und Exportieren von Datendeklarationen finden Sie unter [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
## Beispiel  
 Durch das Verknüpfen der beiden folgenden Module wird LNK4049 generiert.  Das erste Modul generiert eine Objektdatei, die eine einzelne exportierte Funktion enthält.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## Beispiel  
 Das zweite Modul generiert eine Objektdatei, die eine Vorwärtsdeklaration zu der im ersten Modul exportierten Funktion sowie einen Aufruf dieser Funktion in der `main`\-Funktion enthält.  Durch das Verknüpfen dieses Moduls mit dem ersten Modul wird LNK4049 generiert.  Diese Warnung kann vermieden werden, indem die `__declspec(dllimport)`\-Deklaration entfernt wird.  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## Siehe auch  
 [Linkertoolwarnung LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)