---
title: const- und volatile-Zeiger | Microsoft Docs
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
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
caps.latest.revision: 10
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: bebd757f304de2377ab2337e5b41a577a2b492b6
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="const-and-volatile-pointers"></a>const- und volatile-Zeiger
Die [const](../cpp/const-cpp.md) und [volatile](../cpp/volatile-cpp.md) Schlüsselwörter ändern, wie Zeiger behandelt werden. Die **const** -Schlüsselwort Gibt an, dass der Zeiger nach der Initialisierung nicht geändert werden kann; der Zeiger ist danach vor Änderungen geschützt.  
  
 Das `volatile`-Schlüsselwort gibt an, dass der Wert, der dem folgenden Namen zugeordnet ist, durch andere Aktionen als die in der Benutzeranwendung bearbeitet werden kann. Daher ist das `volatile`-Schlüsselwort zum Deklarieren von Objekten im freigegebenen Speicher nützlich, auf den durch mehrere Prozesse oder globale Datenbereiche zugegriffen werden kann, die für die Kommunikation verwendet werden, ohne dass Dienstroutinen unterbrochen werden.  
  
 Wenn ein Name als `volatile` deklariert ist, wird der Wert vom Compiler jedes Mal neu aus dem Arbeitsspeicher geladen, wenn ein Zugriff durch das Programm erfolgt. Dies reduziert die mögliche Optimierung erheblich. Wenn sich der Zustand eines Objekts unerwartet ändern kann, ist dies jedoch die einzige Möglichkeit, vorhersagbare Programmleistung sicherzustellen.  
  
 Deklarieren Sie das Objekt, das der Zeiger zeigt als **const** oder `volatile`, verwenden Sie eine Deklaration der Form:  
  
```  
const char *cpch;  
volatile char *vpch;  
```  
  
 Den Wert des Zeigers deklariert – d. h. die tatsächliche Adresse, die im Zeiger gespeichert – als **const** oder `volatile`, verwenden Sie eine Deklaration der Form:  
  
```  
char * const pchc;  
char * volatile pchv;  
```  
  
 Die Programmiersprache C++ verhindert Zuweisungen, die Änderung eines Objekts die Möglichkeit bietet, oder als Zeiger deklariert **const**. Diese Zuweisungen würden die Informationen entfernen, mit denen das Objekt oder der Zeiger deklariert wurde, und dadurch den Zweck der ursprünglichen Deklaration entfremden. Betrachten Sie hierzu die folgenden Deklarationen:  
  
```  
const char cch = 'A';  
char ch = 'B';  
```  
  
 Erhält die vorhergehenden Deklarationen von zwei Objekten (`cch`, des Typs **const Char**, und `ch`, des Typs **Char)**, die folgenden Deklaration/Initialisierungen gültig sind:  
  
```  
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Die folgende Deklaration/folgenden Initialisierungen sind fehlerhaft.  
  
```  
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 Die Deklaration von `pch2` deklariert einen Zeiger, mit dem ein konstantes Objekt möglicherweise geändert wird, und ist daher nicht zulässig. Die Deklaration von `pch3` gibt an, dass der `pointer`, nicht das Objekt konstant ist. Die Deklaration ist aus demselben Grund unzulässig, aus dem die `pch2`-Deklaration nicht zulässig ist.  
  
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
  
 Als Zeiger deklariert `volatile`, oder als eine Mischung von **const** und `volatile`, befolgen die gleichen Regeln.  
  
 Zeiger auf **const** Objekte werden häufig wie folgt in Funktionsdeklarationen verwendet:  
  
```  
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Die vorhergehende Anweisung deklariert eine Funktion, [Strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), in der zwei der drei Argumente vom typzeiger auf `char`. Da die Argumente nach Verweis übergeben werden und nicht anhand des Werts die Funktion wäre sowohl ändern `strDestination` und `strSource` Wenn `strSource` wurden nicht als deklariert **const**. Die Deklaration von `strSource` als **const** wird sichergestellt, dass dem Aufrufer `strSource` kann nicht von der aufgerufenen Funktion geändert werden.  
  
> [!NOTE]
>  Da es eine standardkonvertierung von ist *Typename* ** \* ** auf **const** *Typename* ** \* **, es ist zulässig, übergeben Sie ein Argument des Typs **Char \* ** auf [Strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Umgekehrt ist dies jedoch nicht "true"; keine implizite Konvertierung existiert, zum Entfernen der **const** Attribut aus einem Objekt oder Zeiger.  
  
 Ein **const** Zeiger eines bestimmten Typs in einen Zeiger des gleichen Typs zugewiesen werden kann. Ein Zeiger, die ist jedoch nicht **const** kann nicht zugewiesen werden, um eine **const** Zeiger. Der folgende Code zeigt korrekte und inkorrekte Zuweisungen:  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Zeiger](../cpp/pointers-cpp.md)
