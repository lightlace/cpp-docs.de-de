---
title: "Regeln und Einschr&#228;nkungen f&#252;r dllimport/dllexport"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "dllexport-Attribut [C++]"
  - "dllexport-Attribut [C++], Einschränkungen und Regeln"
  - "dllimport-Attribut [C++], Einschränkungen und Regeln"
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Regeln und Einschr&#228;nkungen f&#252;r dllimport/dllexport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
-   Wenn Sie eine Funktion ohne das **dllimport**\- oder `dllexport`\-Attribut deklarieren, wird die Funktion nicht als Teil der DLL\-Schnittstelle betrachtet.  Daher muss die Definition der Funktion in diesem Modul oder in einem anderen Modul desselben Programms vorhanden sein.  Damit die Funktion Teil der DLL\-Schnittstelle wird, müssen Sie die Definition der Funktion im anderen Modul als `dllexport` deklarieren.  Andernfalls wird ein Linkerfehler generiert, wenn der Client erstellt wird.  
  
-   Wenn ein einzelnes Modul im Programm sowohl **dllimport**\- als auch `dllexport`\-Deklarationen für dieselbe Funktion enthält, hat das `dllexport`\-Attribut Vorrang vor dem **dllimport**\-Attribut.  Es wird jedoch eine Compilerwarnung ausgegeben.  Beispiel:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllExport void func1( void );   /* Warning; dllexport */  
                                       /* takes precedence. */  
  
    ```  
  
-   Sie können keinen statischen Datenzeiger mit der Adresse eines Datenobjekts, das mit dem **dllimport**\-Attribut deklariert wird, initialisieren.  Durch folgenden Code werden z. B. Fehler verursacht:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport int i;  
       .  
       .  
       .  
       int *pi = &i;                           /* Error */  
  
       void func2()  
       {  
          static int *pi = &i;                   /* Error */  
       }  
  
    ```  
  
-   Das Initialisieren eines statischen Funktionszeigers mit der Adresse einer Funktion, die mit **dllimport** deklariert ist, legt den Zeiger auf die Adresse des DLL\-Importthunks \(ein Codestub, der die Steuerung an die Funktion übergibt\) anstatt auf die Adresse der Funktion fest.  Diese Zuweisung generiert keine Fehlermeldung:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void   
       .  
       .  
       .  
       static void ( *pf )( void ) = &func1;   /* No Error */  
  
       void func2()  
       {  
          static void ( *pf )( void ) = &func1;  /* No Error */  
       }  
  
    ```  
  
-   Da ein Programm, das das Attribut `dllexport` in der Deklaration des Objekts enthält, die Definition für dieses Objekt bereitstellen muss, können Sie einen globalen oder lokalen statischen Funktionszeiger mit der Adresse der `dllexport`\-Funktion initialisieren.  Ebenso können Sie einen globalen oder lokalen statischen Datenzeiger mit der Adresse eines `dllexport`\-Datenobjekts initialisieren.  Beispiel:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllImport int i;  
  
       DllExport void func1( void );  
       DllExport int i;  
       .  
       .  
       .  
       int *pi = &i;                            /* Okay */  
       static void ( *pf )( void ) = &func1;    /* Okay */  
  
       void func2()  
       {  
          static int *pi = i;                     /* Okay */  
          static void ( *pf )( void ) = &func1;   /* Okay */  
       }  
  
    ```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Import\- und Exportfunktionen einer DLL](../c-language/dll-import-and-export-functions.md)