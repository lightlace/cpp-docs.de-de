---
title: const- und volatile-Zeiger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- volatile keyword [C++], and pointers
- pointers, and const
- pointers, and volatile
- const keyword [C++], volatile pointers
ms.assetid: 0c92dc6c-400e-4342-b345-63ddfe649d7e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52550df1ca89ec1252fc2910bf27598d51302495
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212260"
---
# <a name="const-and-volatile-pointers"></a>const- und volatile-Zeiger
Die [const](../cpp/const-cpp.md) und [flüchtige](../cpp/volatile-cpp.md) Schlüsselwörter zu ändern, wie Zeiger behandelt werden. Die **const** -Schlüsselwort Gibt an, dass der Zeiger nach der Initialisierung nicht geändert werden kann; der Zeiger ist danach vor Änderungen geschützt.  
  
 Die **flüchtige** -Schlüsselwort Gibt an, dass der folgende Name der Wert von Aktionen als die in der benutzeranwendung geändert werden kann. Aus diesem Grund die **flüchtige** -Schlüsselwort ist gut geeignet zum Deklarieren von Objekten im freigegebenen Speicher, die durch mehrere Prozesse oder globale Datenbereiche, die für die Kommunikation mit Dienstroutinen zugegriffen werden kann.  
  
 Wenn ein Name wird als deklariert **flüchtige**, der Compiler den Wert aus dem Arbeitsspeicher lädt jedes Mal durch das Programm erfolgt erneut. Dies reduziert die mögliche Optimierung erheblich. Wenn sich der Zustand eines Objekts unerwartet ändern kann, ist dies jedoch die einzige Möglichkeit, vorhersagbare Programmleistung sicherzustellen.  
  
 Deklarieren Sie das Objekt verweist der Zeiger als **const** oder **flüchtige**, verwenden Sie eine Deklaration des Formulars:  
  
```cpp 
const char *cpch;  
volatile char *vpch;  
```  
  
 Den Wert des Zeigers deklariert, d. h. die tatsächliche Adresse, die im Zeiger gespeichert – als **const** oder **flüchtige**, verwenden Sie eine Deklaration des Formulars:  
  
```cpp 
char * const pchc;  
char * volatile pchv;  
```  
  
 Die Programmiersprache C++ verhindert Zuweisungen, die Änderung eines Objekts ermöglichen oder Zeiger deklariert als **const**. Diese Zuweisungen würden die Informationen entfernen, mit denen das Objekt oder der Zeiger deklariert wurde, und dadurch den Zweck der ursprünglichen Deklaration entfremden. Betrachten Sie hierzu die folgenden Deklarationen:  
  
```cpp 
const char cch = 'A';  
char ch = 'B';  
```  
  
 Erhalten die vorherigen Deklarationen von zwei Objekten (`cch`, des Typs **const Char**, und `ch`, des Typs **Char)**, die folgenden Deklaration/Initialisierungen gültig sind:  
  
```cpp 
const char *pch1 = &cch;  
const char *const pch4 = &cch;  
const char *pch5 = &ch;  
char *pch6 = &ch;  
char *const pch7 = &ch;  
const char *const pch8 = &ch;  
```  
  
 Die folgende Deklaration/folgenden Initialisierungen sind fehlerhaft.  
  
```cpp 
char *pch2 = &cch;   // Error  
char *const pch3 = &cch;   // Error  
```  
  
 Die Deklaration von `pch2` deklariert einen Zeiger, mit dem ein konstantes Objekt möglicherweise geändert wird, und ist daher nicht zulässig. Die Deklaration von `pch3` gibt an, dass der Zeiger konstant ist nicht das Objekt die Deklaration ist nicht zulässig, aus demselben Grund der `pch2` Deklaration ist nicht zulässig.  
  
 Die folgenden acht Zuweisungen zeigen die Zuweisung durch einen Zeiger und die Änderung des Zeigerwerts für die vorhergehenden Deklarationen. Gehen Sie vorerst davon aus, dass die Initialisierung für `pch1` durch `pch8` korrekt war.  
  
```cpp 
*pch1 = 'A';  // Error: object declared const  
pch1 = &ch;   // OK: pointer not declared const  
*pch2 = 'A';  // OK: normal pointer  
pch2 = &ch;   // OK: normal pointer  
*pch3 = 'A';  // OK: object not declared const  
pch3 = &ch;   // Error: pointer declared const  
*pch4 = 'A';  // Error: object declared const  
pch4 = &ch;   // Error: pointer declared const  
```  
  
 Zeiger deklariert als **flüchtige**, oder als eine Mischung von **const** und **flüchtige**, befolgen die gleichen Regeln.  
  
 Zeiger auf **const** Objekte werden häufig wie folgt in Funktionsdeklarationen verwendet:  
  
```cpp 
errno_t strcpy_s( char *strDestination, size_t numberOfElements, const char *strSource );  
```  
  
 Die vorhergehende Anweisung deklariert eine Funktion, [Strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), wobei zwei der drei Argumente des Typs Zeiger zu sind **Char**. Da die Argumente als Verweis übergeben werden und nicht anhand des Werts sähe die Funktion beide ändern `strDestination` und `strSource` Wenn `strSource` wurden nicht als deklariert **const**. Die Deklaration von `strSource` als **const** stellt sicher, dass dem Aufrufer `strSource` kann nicht von der aufgerufenen Funktion geändert werden.  
  
> [!NOTE]
> Da es eine standardkonvertierung von ist *Typename* <strong>\*</strong> zu **const** *Typename* <strong>\*</strong>, es ist zulässig, ein Argument des Typs übergeben `char *` zu [Strcpy_s](../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md). Das Gegenteil ist jedoch nicht "true"; keine implizite Konvertierung existiert, zum Entfernen der **const** Attribut aus einem Objekt oder Zeiger.  
  
 Ein **const** Zeiger eines bestimmten Typs in einen Zeiger des gleichen Typs zugewiesen werden kann. Ein Zeiger, die ist jedoch nicht **const** kann nicht zugewiesen werden, um eine **const** Zeiger. Der folgende Code zeigt korrekte und inkorrekte Zuweisungen:  
  
```cpp 
// const_pointer.cpp  
int *const cpObject = 0;  
int *pObject;  
  
int main() {  
pObject = cpObject;  
cpObject = pObject;   // C3892  
}  
```  
  
 Das folgende Beispiel zeigt, wie ein Objekt als Konstante deklariert wird, wenn ein Zeiger auf einen Zeiger auf ein Objekt vorhanden ist.  
  
```cpp 
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