---
title: "const- und volatile-Zeiger | Microsoft Docs"
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
  - "const-Schlüsselwort [C++], volatile-Zeiger"
  - "Zeiger, Und const"
  - "Zeiger, Und volatile"
  - "volatile-Schlüsselwort [C++], Und Zeiger"
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# const- und volatile-Zeiger
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Schlüsselwörter [const](../cpp/const-cpp.md) und [volatile](../cpp/volatile-cpp.md) ändern, wie Zeiger behandelt werden.  Das **const**\-Schlüsselwort gibt an, dass der Zeiger nach der Initialisierung nicht geändert werden kann. Der Zeiger ist danach vor Änderungen geschützt.  
  
 Das `volatile`\-Schlüsselwort gibt an, dass der Wert, der dem folgenden Namen zugeordnet ist, durch andere Aktionen als die in der Benutzeranwendung bearbeitet werden kann.  Daher ist das `volatile`\-Schlüsselwort zum Deklarieren von Objekten im freigegebenen Speicher nützlich, auf den durch mehrere Prozesse oder globale Datenbereiche zugegriffen werden kann, die für die Kommunikation verwendet werden, ohne dass Dienstroutinen unterbrochen werden.  
  
 Wenn ein Name als `volatile` deklariert ist, wird der Wert vom Compiler jedes Mal neu aus dem Arbeitsspeicher geladen, wenn ein Zugriff durch das Programm erfolgt.  Dies reduziert die mögliche Optimierung erheblich.  Wenn sich der Zustand eines Objekts unerwartet ändern kann, ist dies jedoch die einzige Möglichkeit, vorhersagbare Programmleistung sicherzustellen.  
  
 Um das Objekt, auf das der Zeiger verweist, als **const** oder `volatile` zu deklarieren, verwenden Sie eine Deklaration im folgenden Format:  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 Um den Wert des Zeigers, d. h. die tatsächliche Adresse, die im Zeiger gespeichert ist, als **const** oder `volatile` zu deklarieren, verwenden Sie eine Deklaration im folgenden Format:  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 Die Programmiersprache C\+\+ verhindert Zuweisungen, die Änderung eines Objekts oder Zeigers ermöglichen würden, die als **const** deklariert wurden.  Diese Zuweisungen würden die Informationen entfernen, mit denen das Objekt oder der Zeiger deklariert wurde, und dadurch den Zweck der ursprünglichen Deklaration entfremden.  Betrachten Sie hierzu die folgenden Deklarationen:  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 Bei den vorherigen Deklarationen von zwei Objekten \(`cch` vom Typ **const char** und `ch` vom Typ **char\)** ist die folgende Deklaration\/Initialisierungen gültig:  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Die folgende Deklaration\/folgenden Initialisierungen sind fehlerhaft.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 Die Deklaration von `pch2` deklariert einen Zeiger, mit dem ein konstantes Objekt möglicherweise geändert wird, und ist daher nicht zulässig.  Die Deklaration von `pch3` gibt an, dass der `pointer`, nicht das Objekt konstant ist. Die Deklaration ist aus demselben Grund unzulässig, aus dem die `pch2`\-Deklaration nicht zulässig ist.  
  
 Die folgenden acht Zuweisungen zeigen die Zuweisung durch einen Zeiger und die Änderung des Zeigerwerts für die vorhergehenden Deklarationen. Gehen Sie vorerst davon aus, dass die Initialisierung für `pch1` durch `pch8` korrekt war.  
  
```  
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 Zeiger, die als `volatile` oder als Kombination aus **const** und `volatile` deklariert werden, befolgen die gleichen Regeln.  
  
 Zeiger auf **const**\-Objekte werden oft wie folgt in Funktionsdeklarationen verwendet:  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Die vorhergehende Anweisung deklariert eine Funktion, [strcpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), in der zwei der drei Argumente vom Typ Zeiger auf `char` sind.  Da die Argumente durch einen Verweis und nicht als Wert übergeben werden, könnte die Funktion sowohl `strDestination` als auch `strSource` ändern, wenn `strSource` nicht als **const** deklariert wäre.  Die Deklaration von `strSource` als **const** gewährleistet für den Aufrufer, dass `strSource` nicht von der aufgerufenen Funktion geändert werden kann.  
  
> [!NOTE]
>  Da es sich um eine Standardkonvertierung von *typename* **\*** zu **const** *typename* **\*** handelt, ist es zulässig, ein Argument des Typs **char \*** an [strcpy\_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md) zu übergeben.  Umgekehrt ist dies jedoch nicht wahr, da keine implizite Konvertierung existiert, um das **const**\-Attribut aus einem Objekt oder Zeiger zu entfernen.  
  
 Ein **const**\-Zeiger eines angegebenen Typs kann einem Zeiger des gleichen Typs zugewiesen werden.  Allerdings kann ein Zeiger, der nicht **const** ist, keinem **const**\-Zeiger zugewiesen werden.  Der folgende Code zeigt korrekte und inkorrekte Zuweisungen:  
  
```  
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 Das folgende Beispiel zeigt, wie ein Objekt als Konstante deklariert wird, wenn ein Zeiger auf einen Zeiger auf ein Objekt vorhanden ist.  
  
```  
// const_pointer2.cpp  
struct X {  
   X(int i) : m_i(i) { }  
   int m_i;  
};  
  
int main() {  
   // correct  
   const X cx(10);  
   const X * pcx = &cx;  
   const X ** ppcx = &pcx;  
  
   // also correct  
   X const cx2(20);  
   X const * pcx2 = &cx2;  
   X const ** ppcx2 = &pcx2;  
}  
```  
  
## Siehe auch  
 [Zeiger](../cpp/pointers-cpp.md)