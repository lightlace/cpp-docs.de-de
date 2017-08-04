---
title: Quelldateien und Quellprogramme | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- files [C++], source
- programs [C++], source
- source files, specifying in compiler
- source programs
ms.assetid: 18bb2826-17da-48e5-92a2-10e649f1bc9f
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: a9bb5e470dc4d3da5662a15e3b7ed5e9bc60d01f
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="source-files-and-source-programs"></a>Quelldateien und Quellprogramme
Ein Quellprogramm kann in eine oder mehrere "Quelldateien" oder in "Übersetzungseinheiten" aufgeteilt werden. Die Eingabe in den Compiler wird als "Übersetzungseinheit" bezeichnet.  
  
## <a name="syntax"></a>Syntax  
 *translation-unit*:  
 *external-declaration*  
  
 *translation-unit external-declaration*  
  
 *external-declaration*:  
 *function-definition*  
  
 *declaration*  
  
 [Übersicht über Deklarationen](../c-language/overview-of-declarations.md) gibt die Syntax für das `declaration`-Nichtterminal an, und in der *Präprozessorreferenz* wird erläutert, wie die [Übersetzungseinheit](../preprocessor/phases-of-translation.md) verarbeitet wird.  
  
> [!NOTE]
>  Eine Erläuterung der ANSI-Syntaxkonventionen erhalten Sie in der Einführung zur [Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md).  
  
 Die Komponenten einer Übersetzungseinheit sind externe Deklarationen, die Funktionsdefinitionen und Bezeichnerdeklarationen enthalten. Diese Deklarationen und Definitionen können sich in den Quelldateien, Headerdateien, Bibliotheken und anderen Dateien befinden, die das Programm benötigt. Sie müssen jede Übersetzungseinheit kompilieren und die resultierenden Objektdateien verknüpfen, um ein Programm zu erstellen.  
  
 Ein Quellprogramm ist bei C eine Auflistung von Direktiven, Pragmas, Deklarationen, Definitionen, Anweisungsblöcken und Funktionen. Um als gültige Komponenten eines Microsoft-C-Programms zu gelten, muss jede Komponente die Syntax aufweisen, die in diesem Buch beschrieben wird. Die Komponenten können jedoch (gemäß den Regeln in diesem Buch) in beliebiger Reihenfolge im Programm angezeigt werden. Allerdings wirkt sich der Speicherort dieser Komponenten in einem Programm darauf aus, wie Variablen und Funktionen in einem Programm verwendet werden können. (Weitere Informationen erhalten Sie unter [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md).)  
  
 Quelldateien müssen keine ausführbaren Anweisungen enthalten. Beispielsweise finden Sie es vielleicht hilfreich, Definitionen von Variablen in einer Quelldatei einzufügen und dann Verweise auf diese Variablen in anderen Quelldateien, die diese verwenden, zu deklarieren. Diese Vorgehensweise erleichtert das Suchen und ggf. Aktualisieren der Definitionen. Aus demselben Grund werden Konstanten und Makros häufig in separaten Dateien strukturiert, die "Includedateien" oder "Headerdateien" genannt werden und auf die nach Bedarf in Quelldateien verwiesen werden kann. Weitere Informationen zu [Makros](../preprocessor/macros-c-cpp.md) und [Includedateien](../preprocessor/hash-include-directive-c-cpp.md) finden Sie in der *Präprozessorreferenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmstruktur](../c-language/program-structure.md)
