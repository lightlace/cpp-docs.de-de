---
title: Linkertoolwarnung Lnk4049 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4049
dev_langs:
- C++
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b50dadc9c160ac8902cedcd60c954b565dce6e24
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302372"
---
# <a name="linker-tools-warning-lnk4049"></a>Linkertoolwarnung LNK4049
Lokal definiertes Symbol 'Symbol' nicht importiert  
  
 Das Symbol wurde sowohl aus exportiert und an das Programm importiert.  
  
 Diese Warnung wird vom Linker generiert, wenn Sie ein Symbol mit deklarieren die `__declspec(dllexport)` Storage-Class-Attribut in der Datei für ein Objekt, und verweisen sie mit der `__declspec(dllimport)` Attribut in einer anderen.  
  
 Linkertoolwarnung LNK4049 ist eine allgemeinere Version von [Linker Tools Warning LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md). Wenn nicht bestimmt werden kann von der Funktion das importierte Symbol verwiesen wurde, generiert der Linker Warnung LNK4049.  
  
 Allgemeine Fälle, in denen LNK4049, statt LNK4217 generiert wird, sind:  
  
-   Inkrementelles Verknüpfen mit der [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) Option.  
  
-   Ausführen der Optimierung des gesamten Programms mithilfe der [/LTCG](../../build/reference/ltcg-link-time-code-generation.md) Option.  
  
 Um LNK4049 zu beheben, führen Sie eine der folgenden aus:  
  
-   Entfernen Sie die `__declspec(dllimport)` benennen-Deklaration aus der Vorwärtsdeklaration des Symbols, das LNK4049 ausgelöst hat. Sie können nach Symbolen in einem binären Bild suchen, mit der **DUMPBIN** Hilfsprogramm. Die **DUMPBIN/SYMBOLE** Schalter zeigt der COFF-Symboltabelle des Abbilds an. Weitere Informationen zu den **DUMPBIN** -Dienstprogramm finden Sie unter [DUMPBIN-Referenz](../../build/reference/dumpbin-reference.md).  
  
-   Vorübergehendes Deaktivieren von inkrementelles Verknüpfen und die Optimierung des gesamten Programms. Erneutes Kompilieren der Anwendung generiert Linkertoolwarnung LNK4217, darunter der Name der Funktion wird von dem das importierte Symbol verwiesen wurde. Entfernen Sie die `__declspec(dllimport)` Deklaration aus der importierten Symbole und Enable inkrementelles Verknüpfen oder die Optimierung des gesamten Programms nach Bedarf.  
  
 Obwohl der endgültige generierten Code ordnungsgemäß erfolgt, ist der Code zum Aufrufen der importierten Funktion weniger effizient als direkter Aufruf der Funktion. Diese Warnung wird nicht angezeigt, wenn Sie Kompilieren mit der Option ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Weitere Informationen zum Importieren und Exportieren von Datendeklarationen, finden Sie unter [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md).  
  
## <a name="example"></a>Beispiel  
 Verknüpfen die folgenden beiden Module wird LNK4049 generiert. Das erste Modul generiert eine Objektdatei, die eine exportierte Funktion enthält.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Das zweite Modul generiert eine Objektdatei, die eine Vorwärtsdeklaration für die im ersten Modul zusammen mit einem Aufruf dieser Funktion in exportierten Funktion enthält die `main` Funktion. Verknüpfen dieses Modul mit dem ersten Modul wird LNK4049 generiert. Entfernen der `__declspec(dllimport)` Deklaration die Warnung aufgelöst wird.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Linkertoolwarnung Lnk4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)