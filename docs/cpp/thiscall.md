---
title: __thiscall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __thiscall
- __thiscall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __thiscall keyword [C++]
ms.assetid: a6a22dd2-0101-4885-b33b-22f6057965df
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 41dd6d823d9889f5ce0216b27ad01a8d29bc57f6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="thiscall"></a>__thiscall
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die `__thiscall`-Aufrufkonvention wird für Memberfunktionen verwendet und ist die Standardaufrufkonvention, die von C++-Memberfunktionen verwendet wird, die keine variablen Argumente verwenden. Unter `__thiscall` entleert der Aufgerufene den Stapel, was für `vararg`-Funktionen nicht möglich ist. Argumente werden von rechts nach links auf den Stapel geschoben, wobei der `this`-Zeiger auf der x86-Architektur über das Register "ECX" übergeben wird, und nicht auf dem Stapel.  
  
 Die Verwendung von `__thiscall` ist in Klassen sinnvoll, deren Memberfunktionen standardmäßig `__clrcall` verwenden. In diesem Fall können Sie `__thiscall` verwenden, um individuelle Memberfunktionen aus dem systemeigenen Code aufrufbar zu machen.  
  
 Beim Kompilieren mit [/CLR: pure](../build/reference/clr-common-language-runtime-compilation.md), sind alle Funktionen und Funktionszeiger `__clrcall` sofern nicht anders angegeben. Die Compileroptionen **/clr:pure** und **/clr:safe** sind in Visual Studio 2015 veraltet.  
  
 In Versionen vor Visual C++ 2005 konnte die thiscall-Aufrufkonvention nicht explizit in einem Programm angegeben werden, da `thiscall` kein Schlüsselwort war.  
  
 `vararg`-Memberfunktionen verwenden die `__cdecl`-Aufrufkonvention. Alle Funktionsargumente werden auf dem Stapel abgelegt, wobei der `this`-Zeiger zuletzt auf dem Stapel abgelegt wird.  
  
 Da diese Aufrufkonvention nur für C++ gültig ist, gibt es kein Schema zur C-Namensergänzung.  
  
 Auf ARM und [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Computern `__thiscall` akzeptiert und vom Compiler ignoriert.  
  
 Wenn die Funktion bei nicht statischen Klassenfunktionen abweichend definiert ist, muss der Aufrufkonventionsmodifizierer nicht in der abweichenden Definition angegeben werden. Das bedeutet, dass für nicht statische Membermethoden der Klasse zum Zeitpunkt der Definition die während der Deklaration angegebene Aufrufkonvention angenommen wird.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md)
