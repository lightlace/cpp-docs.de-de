---
title: Allgemeine Regeln und Einschränkungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19a704036ffac974bc99d93996d083733f59d0d4
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943895"
---
# <a name="general-rules-and-limitations"></a>Allgemeine Regeln und Einschränkungen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
  
-   Wenn Sie eine Funktion deklariert oder ein ohne Objekt die **Dllimport** oder **Dllexport** -Attribut, Funktion oder des Objekts wird nicht als Teil der DLL-Schnittstelle betrachtet. Daher muss die Definition der Funktion oder des Objekts in diesem Modul oder in einem anderen Modul desselben Programms vorhanden sein. Um der Funktion oder das Objekt Teil der DLL-Schnittstelle zu machen, müssen Sie die Definition der Funktion oder des Objekts im anderen Modul als deklarieren **Dllexport**. Andernfalls wird ein Linkerfehler generiert.  
  
     Wenn Sie eine Funktion deklariert oder ein Objekt mit der **Dllexport** -Attribut seiner Definition muss in einem Modul desselben Programms angezeigt werden. Andernfalls wird ein Linkerfehler generiert.  
  
-   Wenn ein einzelnes Modul im Programm sowohl enthält **Dllimport** und **Dllexport** -Deklarationen für dieselbe Funktion oder des Objekts, das **Dllexport** -Attribut hat Vorrang vor über die **Dllimport** Attribut. Es wird jedoch eine Compilerwarnung ausgegeben. Zum Beispiel:  
  
    ```cpp 
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   In C++ können Sie einen global deklarierten oder statischen lokalen Datenzeiger initialisieren oder die Adresse eines Objekts deklariert mit dem **Dllimport** -Attribut, das einen Fehler in c generiert wird. Darüber hinaus können Sie einen statischen lokalen Funktionszeiger mit der Adresse einer Funktion, die mit deklariert Initialisieren der **Dllimport** Attribut. In C legt eine solche Zuweisung den Zeiger auf die Adresse des DLL-Importthunks (ein Codestub, der die Steuerung an die Funktion übergibt) anstatt auf die Adresse der Funktion fest. In C++ wird der Zeiger auf die Adresse der Funktion festgelegt. Zum Beispiel:  
  
    ```cpp 
    __declspec( dllimport ) void func1( void );  
    __declspec( dllimport ) int i;  
  
    int *pi = &i;                             // Error in C  
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,  
                                              // function in C++  
  
    void func2()  
    {  
       static int *pi = &i;                  // Error in C  
       static void ( *pf )( void ) = &func1; // Address of thunk in C,  
                                             // function in C++  
    }  
    ```  
  
     Aber da ein Programm, enthält die **Dllexport** Attribut in der Deklaration eines Objekts muss die Definition für dieses Objekt an einer beliebigen Stelle im Programm bereitstellen, initialisieren Sie einen globalen oder lokalen statischen Funktionszeiger mit die Adresse einer **Dllexport** Funktion. Sie können auf ähnliche Weise initialisieren, einen globalen oder lokalen statischen Datenzeiger mit der Adresse einer **Dllexport** Datenobjekt. Zum Beispiel generiert der folgende Code keine Fehler in C oder C++:  
  
    ```cpp 
    __declspec( dllexport ) void func1( void );  
    __declspec( dllexport ) int i;  
  
    int *pi = &i;                              // Okay  
    static void ( *pf )( void ) = &func1;      // Okay  
  
    void func2()  
    {  
        static int *pi = &i;                   // Okay  
        static void ( *pf )( void ) = &func1;  // Okay  
    }  
    ```  
  
-   Wenn Sie anwenden **Dllexport** in einer normalen Klasse, die eine Basisklasse verfügt, die nicht als gekennzeichnet ist **Dllexport**, generiert der Compiler C4275.  
  
     Der Compiler generiert dieselbe Warnung, wenn die Basisklasse eine Spezialisierung einer Klassenvorlage ist. Um dieses Problem umgehen, markieren Sie die Basisklasse mit **Dllexport**. Das Problem bei einer Spezialisierung einer Klassenvorlage ist, wo die **__declspec(dllexport)**; Sie sind nicht zulässig, um die Klassenvorlage zu markieren. Stattdessen explizit instanziiert die Klassenvorlage und markieren Sie diese explizite Instanziierung mit **Dllexport**. Zum Beispiel:  
  
    ```cpp 
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Diese Problemumgehung funktioniert nicht, wenn das Vorlagenargument die ableitende Klasse ist. Zum Beispiel:  
  
    ```cpp 
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Da dies allgemeines Muster für Vorlagen ist, ändert der Compiler die Semantik der **Dllexport** , wenn es auf eine Klasse angewendet wird, die eine oder mehrere Basisklassen verfügt und mindestens einer der Basisklassen eine Spezialisierung einer Klassenvorlage ist . In diesem Fall wendet der Compiler implizit **Dllexport** auf die spezialisierungen von Klassenvorlagen. Gehen können und eine Warnung nicht abgerufen werden:  
  
    ```cpp 
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)