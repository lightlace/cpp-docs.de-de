---
title: "Allgemeine Regeln und Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Allgemeine Regeln und Einschr&#228;nkungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
  
-   Wenn Sie eine Funktion oder ein Objekt ohne das **dllimport**\- oder `dllexport`\-Attribut deklarieren, wird die Funktion oder das Objekt nicht als Teil der DLL\-Schnittstelle erkannt.  Daher muss die Definition der Funktion oder des Objekts in diesem Modul oder in einem anderen Modul desselben Programms vorhanden sein.  Damit die Funktion oder das Objekt Teil der DLL\-Schnittstelle wird, müssen Sie die Definition der Funktion oder des Objekts im anderen Modul als `dllexport` deklarieren.  Andernfalls wird ein Linkerfehler generiert.  
  
     Wenn Sie eine Funktion oder ein Objekt mit dem `dllexport`\-Attribut deklarieren, muss die zugehörige Definition in einem Modul desselben Programms enthalten sein.  Andernfalls wird ein Linkerfehler generiert.  
  
-   Wenn ein einzelnes Modul im Programm sowohl **dllimport** als auch `dllexport`\-Deklarationen für dieselbe Funktion oder dasselbe Objekt enthält, hat das `dllexport`\-Attribut Vorrang vor dem **dllimport**\-Attribut.  Es wird jedoch eine Compilerwarnung ausgegeben.  Beispiel:  
  
    ```  
    __declspec( dllimport ) int i;  
    __declspec( dllexport ) int i;   // Warning; inconsistent;  
                                     // dllexport takes precedence.  
    ```  
  
-   In C\+\+ können Sie einen global deklarierten oder statischen lokalen Datenzeiger initialisieren oder die Adresse eines Datenobjekts verwenden, das mit dem **dllimport**\-Attribut deklariert wird, wodurch ein Fehler in C generiert wird.  Außerdem können Sie einen statischen lokalen Funktionszeiger mit der Adresse einer Funktion initialisieren, die mit dem **dllimport**\-Attribut deklariert wird.  In C legt eine solche Zuweisung den Zeiger auf die Adresse des DLL\-Importthunks \(ein Codestub, der die Steuerung an die Funktion übergibt\) anstatt auf die Adresse der Funktion fest.  In C\+\+ wird der Zeiger auf die Adresse der Funktion festgelegt.  Beispiel:  
  
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
  
     Da ein Programm, das das Attribut `dllexport` in der Deklaration eines Objekts enthält, die Definition für dieses Objekt an irgendeiner Stelle im Programm bereitstellen muss, können Sie einen Zeiger der globalen oder lokalen statischen Funktion mit der Adresse der `dllexport`\-Funktion initialisieren.  Ebenso können Sie einen globalen oder lokalen statischen Datenzeiger mit der Adresse eines `dllexport`\-Datenobjekts initialisieren.  Zum Beispiel generiert der folgende Code keine Fehler in C oder C\+\+:  
  
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
  
-   In Visual C\+\+.NET wurde eine Änderung im Verhalten eingeführt, um die Anwendung von `dllexport` zwischen regulären Klassen und Klassenvorlagenspezialisierungen konsistenter zu machen. Wenn Sie daher `dllexport` in einer normalen Klasse anwenden, die über eine Basisklasse verfügt, die nicht als `dllexport` gekennzeichnet ist, generiert der Compiler "C4275".  
  
     Der Compiler generiert dieselbe Warnung, wenn die Basisklasse eine Spezialisierung einer Klassenvorlage ist.  Um dies zu umgehen, markieren Sie die Basisklasse mit `dllexport`.  Das Problem bei einer Spezialisierung einer Klassenvorlage ist, wo **\_\_declspec\(dllexport\)** eingefügt wird. Sie dürfen die Klassenvorlage nicht markieren.  Instanziieren Sie die Klassenvorlage stattdessen explizit, und markieren Sie diese explizite Instanziierung mit `dllexport`.  Beispiel:  
  
    ```  
    template class __declspec(dllexport) B<int>;  
    class __declspec(dllexport) D : public B<int> {  
    // ...  
    ```  
  
     Diese Problemumgehung funktioniert nicht, wenn das Vorlagenargument die ableitende Klasse ist.  Beispiel:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
     Da dies ein allgemeines Muster für Vorlagen ist, ändert der Compiler die Semantik von `dllexport`, wenn dies auf eine Klasse angewendet wird, die mindestens eine Basisklasse hat, und wenn mindestens eine der Basisklassen eine Spezialisierung einer Klassenvorlage ist.  In diesem Fall wendet der Compiler `dllexport` implizit auf die Spezialisierungen von Klassenvorlagen an.  In Visual C\+\+ .NET kann ein Benutzer Folgendes ausführen, ohne eine Warnung zu erhalten:  
  
    ```  
    class __declspec(dllexport) D : public B<D> {  
    // ...  
    ```  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)