---
title: "init_seg"
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
  - "vc-pragma.init_seg"
  - "init_seg_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Datensegmentinitialisierung [C++]"
  - "init_seg-Pragma"
  - "Pragmas, init_seg"
ms.assetid: 40a5898a-5c85-4aa9-8d73-3d967eb13610
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# init_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt ein Schlüsselwort oder einen Codeabschnitt an, der sich auf die Reihenfolge auswirkt, in der Startcode ausgeführt wird.  
  
## Syntax  
  
```  
  
#pragma init_seg({ compiler | lib | user | "section-name" [, func-name]} )  
```  
  
## Hinweise  
 Die Ausdrücke *Segment* und *Abschnitt* sind in diesem Thema gleichbedeutend.  
  
 Da die Initialisierung eines globalen statischen Objekts ausführenden Code umfassen kann, müssen Sie ein Schlüsselwort angeben, das definiert, wann die Objekte erstellt werden sollen.  Es ist besonders wichtig, das **init\_seg**\-Pragma in DLLs \(Dynamic Link Libraries\) oder Bibliotheken zu verwenden, für die eine Initialisierung erforderlich ist.  
  
 Die Optionen für das **init\_seg**\-Pragma sind:  
  
 **compiler**  
 Reserviert für die Initialisierung der Microsoft C\-Laufzeitbibliothek.  Objekte in dieser Gruppe werden zuerst erstellt.  
  
 **lib**  
 Verfügbar für die Initialisierungen der Klassenbibliotheken von Drittanbietern.  Objekte in dieser Gruppe werden nach denen, die als **compiler** markiert sind, aber vor allen anderen erstellt.  
  
 **Benutzer**  
 Verfügbar für alle beliebigen Benutzer.  Objekte in dieser Gruppe werden zuletzt erstellt.  
  
 *section\-name*  
 Ermöglicht die explizite Angabe des Abschnitts für Initialisierung.  Objekte in einem vom Benutzer angegebenen *section\-name* werden nicht implizit erstellt. Allerdings werden ihre Adressen im Abschnitt eingefügt, der von *section\-name* benannt ist.  
  
 Der angegebene Abschnittsname enthält Zeiger auf Hilfsfunktionen, die die globalen Objekte erstellen, die in diesem Modul nach dem Pragma deklariert wurden.  
  
 Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [\/SECTION](../build/reference/section-specify-section-attributes.md).  
  
 *func\-name*  
 Gibt eine Funktion an, die statt `atexit` aufgerufen werden soll, wenn das Programm beendet wird.  Diese Hilfsfunktion ruft zudem [atexit](../c-runtime-library/reference/atexit.md) mit einem Zeiger auf den Destruktor für das globale Objekt auf.  Wenn Sie einen Funktionsbezeichner im Pragma des Formulars angeben,  
  
```  
int __cdecl myexit (void (__cdecl *pf)(void))  
```  
  
 wird die Funktion anstelle von `atexit` für die Laufzeitbibliothek von C aufgerufen.  Dadurch können Sie eine Liste mit Destruktoren erstellen, die aufgerufen werden müssen, wenn Sie bereit sind, die Objekte zu zerstören.  
  
 Wenn Sie die Initialisierung verzögern müssen \(z. B. in einer DLL\), können Sie den Abschnittsnamen auch explizit angeben.  Anschließend müssen Sie die Konstruktoren für jedes statische Objekt aufrufen.  
  
 Der Bezeichner für die Ersetzung von `atexit` weist keine Anführungszeichen auf.  
  
 Die Objekte werden in den Abschnitten platziert, die von den anderen XXX\_seg\-Pragmas definiert sind.  
  
 Die Objekte, die im Modul deklariert wurden, werden nicht automatisch von der C\-Laufzeit initialisiert.  Sie müssen das selbst tun.  
  
 Standardmäßig sind `init_seg`\-Abschnitte schreibgeschützt.  Wenn der Abschnittsname .CRT ist, legt der Compiler automatisch das Attribut auf schreibgeschützt fest, auch wenn es den Schreibzugriff gestattet hat.  
  
 Sie können **init\_seg** in einer Übersetzungseinheit nicht mehrmals angeben.  
  
 Auch wenn das Objekt über keinen benutzerdefinierten Konstruktor verfügt, einen Konstruktor, der im Code nicht explizit definiert wurde, generiert der Compiler möglicherweise einen, um die v\-table\-Zeiger zu binden.  Deshalb muss der Code den vom Compiler generierten Konstruktor aufrufen.  
  
## Beispiel  
  
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
  
  **A\(\)**  
**A\(\)**  
**A\(\)**  
**~A\(\)**  
**~A\(\)**  
**~A\(\)**   
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)