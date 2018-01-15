---
title: Init_seg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.init_seg
- init_seg_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, init_seg
- init_seg pragma
- data segment initializing [C++]
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69036ffba2143d166c9ac5c55a5b3ec9008b75bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="initseg"></a>init_seg
**C++-spezifisch**  
  
 Gibt ein Schlüsselwort oder einen Codeabschnitt an, der sich auf die Reihenfolge auswirkt, in der Startcode ausgeführt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 Da die Initialisierung eines globalen statischen Objekts ausführenden Code umfassen kann, müssen Sie ein Schlüsselwort angeben, das definiert, wann die Objekte erstellt werden sollen. Es ist besonders wichtig, verwenden Sie die **Init_seg** Pragma in Dynamic Link Libraries (DLLs) oder Bibliotheken, die eine Initialisierung erforderlich ist.  
  
 Die Optionen für die **Init_seg** Pragma sind:  
  
 **Compilerfehler**  
 Reserviert für die Initialisierung der Microsoft C-Laufzeitbibliothek. Objekte in dieser Gruppe werden zuerst erstellt.  
  
 **LIB**  
 Verfügbar für die Initialisierungen der Klassenbibliotheken von Drittanbietern. Objekte in dieser Gruppe werden erstellt, nach denen als gekennzeichnete **Compiler** aber vor allen anderen.  
  
 **Benutzer**  
 Verfügbar für alle beliebigen Benutzer. Objekte in dieser Gruppe werden zuletzt erstellt.  
  
 *Abschnitt-name*  
 Ermöglicht die explizite Angabe des Abschnitts für Initialisierung. Objekte in einem vom Benutzer angegebenen *Abschnittsname* werden nicht implizit erstellt; allerdings werden ihre Adressen im Abschnitt mit dem Namen von platziert *Abschnittsname*.  
  
 Der angegebene Abschnittsname enthält Zeiger auf Hilfsfunktionen, die die globalen Objekte erstellen, die in diesem Modul nach dem Pragma deklariert wurden.  
  
 Eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden, finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 *Func-name*  
 Gibt eine Funktion an, die statt `atexit` aufgerufen werden soll, wenn das Programm beendet wird. Diese Hilfsfunktion ruft zudem [Atexit](../c-runtime-library/reference/atexit.md) mit einem Zeiger auf den Destruktor für das globale Objekt. Wenn Sie einen Funktionsbezeichner im Pragma des Formulars angeben,  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 wird die Funktion anstelle von `atexit` für die Laufzeitbibliothek von C aufgerufen. Dadurch können Sie eine Liste mit Destruktoren erstellen, die aufgerufen werden müssen, wenn Sie bereit sind, die Objekte zu zerstören.  
  
 Wenn Sie die Initialisierung verzögern müssen (z. B. in einer DLL), können Sie den Abschnittsnamen auch explizit angeben. Anschließend müssen Sie die Konstruktoren für jedes statische Objekt aufrufen.  
  
 Der Bezeichner für die Ersetzung von `atexit` weist keine Anführungszeichen auf.  
  
 Die Objekte werden in den Abschnitten platziert, die von den anderen XXX_seg-Pragmas definiert sind.  
  
 Die Objekte, die im Modul deklariert wurden, werden nicht automatisch von der C-Laufzeit initialisiert. Sie müssen das selbst tun.  
  
 Standardmäßig sind `init_seg`-Abschnitte schreibgeschützt. Wenn der Abschnittsname .CRT ist, legt der Compiler automatisch das Attribut auf schreibgeschützt fest, auch wenn es den Schreibzugriff gestattet hat.  
  
 Sie können keine angeben **Init_seg** mehr als einmal in einer Übersetzungseinheit.  
  
 Auch wenn das Objekt über keinen benutzerdefinierten Konstruktor verfügt, einen Konstruktor, der im Code nicht explizit definiert wurde, generiert der Compiler möglicherweise einen, um die v-table-Zeiger zu binden.  Deshalb muss der Code den vom Compiler generierten Konstruktor aufrufen.  
  
## <a name="example"></a>Beispiel  
  
```  
// pragma_directive_init_seg.cpp  
#include <stdio.h>  
#pragma warning(disable : 4075)  
  
typedef void (__cdecl *PF)(void);  
int cxpf = 0;   // number of destructors we need to call  
PF pfx[200];    // pointers to destructors.  
  
int myexit (PF pf) {  
   pfx[cxpf++] = pf;  
   return 0;  
}  
  
struct A {  
   A() { puts("A()"); }  
   ~A() { puts("~A()"); }  
};  
  
// ctor & dtor called by CRT startup code   
// because this is before the pragma init_seg  
A aaaa;   
  
// The order here is important.  
// Section names must be 8 characters or less.  
// The sections with the same name before the $  
// are merged into one section. The order that  
// they are merged is determined by sorting  
// the characters after the $.  
// InitSegStart and InitSegEnd are used to set  
// boundaries so we can find the real functions  
// that we need to call for initialization.  
  
#pragma section(".mine$a", read)  
__declspec(allocate(".mine$a")) const PF InitSegStart = (PF)1;  
  
#pragma section(".mine$z",read)  
__declspec(allocate(".mine$z")) const PF InitSegEnd = (PF)1;  
  
// The comparison for 0 is important.  
// For now, each section is 256 bytes. When they  
// are merged, they are padded with zeros. You  
// can't depend on the section being 256 bytes, but  
// you can depend on it being padded with zeros.  
  
void InitializeObjects () {  
   const PF *x = &InitSegStart;  
   for (++x ; x < &InitSegEnd ; ++x)  
      if (*x) (*x)();  
}  
  
void DestroyObjects () {  
   while (cxpf>0) {  
      --cxpf;  
      (pfx[cxpf])();  
   }  
}  
  
// by default, goes into a read only section  
#pragma init_seg(".mine$m", myexit)  
  
A bbbb;   
A cccc;  
  
int main () {  
   InitializeObjects();  
   DestroyObjects();  
}  
```  
  
```Output  
A()  
A()  
A()  
~A()  
~A()  
~A()  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)