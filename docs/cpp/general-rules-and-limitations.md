---
title: "Allgemeine Regeln und Einschränkungen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f92844e993671a3423c04523ccf4e03f7f7e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="general-rules-and-limitations"></a>Allgemeine Regeln und Einschränkungen
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
  
-   Wenn Sie eine Funktion deklariert oder ein ohne Objekt die **Dllimport** oder `dllexport` -Attribut, Funktion oder des Objekts wird nicht als Teil der DLL-Schnittstelle betrachtet. Daher muss die Definition der Funktion oder des Objekts in diesem Modul oder in einem anderen Modul desselben Programms vorhanden sein. Damit die Funktion oder das Objekt Teil der DLL-Schnittstelle wird, müssen Sie die Definition der Funktion oder des Objekts im anderen Modul als `dllexport` deklarieren. Andernfalls wird ein Linkerfehler generiert.  
  
     Wenn Sie eine Funktion oder ein Objekt mit dem `dllexport`-Attribut deklarieren, muss die zugehörige Definition in einem Modul desselben Programms enthalten sein. Andernfalls wird ein Linkerfehler generiert.  
  
-   Wenn ein einzelnes Modul im Programm sowohl enthält **Dllimport** und `dllexport` -Deklarationen für dieselbe Funktion oder des Objekts, das `dllexport` -Attribut Vorrang gegenüber der **Dllimport** Das Attribut. Es wird jedoch eine Compilerwarnung ausgegeben. Zum Beispiel:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   In C++ können Sie einen global deklarierten oder statischen lokalen Datenzeiger initialisieren oder mit der Adresse eines Datenobjekts mit deklariert die **Dllimport** -Attribut, das einen Fehler in c generiert wird. Darüber hinaus können Sie einen statischen lokalen Funktionszeiger mit der Adresse einer Funktion deklariert mit Initialisieren der **Dllimport** Attribut. In C legt eine solche Zuweisung den Zeiger auf die Adresse des DLL-Importthunks (ein Codestub, der die Steuerung an die Funktion übergibt) anstatt auf die Adresse der Funktion fest. In C++ wird der Zeiger auf die Adresse der Funktion festgelegt. Zum Beispiel:  
  
    ```  
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
  
     Da ein Programm, das das Attribut `dllexport` in der Deklaration eines Objekts enthält, die Definition für dieses Objekt an irgendeiner Stelle im Programm bereitstellen muss, können Sie einen Zeiger der globalen oder lokalen statischen Funktion mit der Adresse der `dllexport`-Funktion initialisieren. Ebenso können Sie einen globalen oder lokalen statischen Datenzeiger mit der Adresse eines `dllexport`-Datenobjekts initialisieren. Zum Beispiel generiert der folgende Code keine Fehler in C oder C++:  
  
    ```  
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
  
-   Wenn Sie anwenden `dllexport` in einer normalen Klasse, die eine Basisklasse verfügt, die nicht als markiert ist `dllexport`, generiert der Compiler C4275.  
  
     Der Compiler generiert dieselbe Warnung, wenn die Basisklasse eine Spezialisierung einer Klassenvorlage ist. Um dies zu umgehen, markieren Sie die Basisklasse mit `dllexport`. Das Problem mit einer Spezialisierung einer Klassenvorlage ist Platzieren der **__declspec(dllexport)**; Sie sind nicht zulässig, um die Klassenvorlage zu markieren. Instanziieren Sie die Klassenvorlage stattdessen explizit, und markieren Sie diese explizite Instanziierung mit `dllexport`. Zum Beispiel:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Diese Problemumgehung funktioniert nicht, wenn das Vorlagenargument die ableitende Klasse ist. Zum Beispiel:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Da dies ein allgemeines Muster für Vorlagen ist, ändert der Compiler die Semantik von `dllexport`, wenn dies auf eine Klasse angewendet wird, die mindestens eine Basisklasse hat, und wenn mindestens eine der Basisklassen eine Spezialisierung einer Klassenvorlage ist. In diesem Fall wendet der Compiler `dllexport` implizit auf die Spezialisierungen von Klassenvorlagen an. Führen Sie folgende Schritte und erhalten eine Warnung nicht möglich:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)