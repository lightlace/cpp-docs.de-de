---
title: "Anonyme Klassentypen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anonyme Klassentypen"
  - "Klassentypen, Anonyme"
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Anonyme Klassentypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassen können anonym sein, d. h. sie können ohne *Bezeichner* deklariert werden.  Dies ist nützlich, wenn Sie einen Klassennamen durch einen `typedef`\- Namen ersetzen, wie im Folgenden gezeigt:  
  
```  
typedef struct  
{  
    unsigned x;  
    unsigned y;  
} POINT;  
```  
  
> [!NOTE]
>  Die Verwendung von anonymen Klassen, die im vorherigen Beispiel gezeigt wird, ist für das Beibehalten der Kompatibilität mit existierendem C\-Code nützlich.  In manchem C\-Code wird hauptsächlich `typedef` zusammen mit anonymen Strukturen verwendet.  
  
 Anonyme Klassen sind außerdem nützlich, wenn Sie möchten, dass ein Verweis auf einen Klassenmember so angezeigt wird, als befände er sich nicht in einer separaten Klasse, wie im Folgenden gezeigt:  
  
```  
struct PTValue  
{  
    POINT ptLoc;  
    union  
    {  
        int  iValue;  
        long lValue;  
    };  
};  
  
PTValue ptv;  
```  
  
 Im vorangehenden Code kann auf `iValue` mithilfe des Objektmember\-Auswahloperators \(**.**\) wie folgt zugegriffen werden:  
  
```  
int i = ptv.iValue;  
```  
  
 Anonyme Klassen unterliegen bestimmten Einschränkungen.  \(Weitere Informationen über anonyme Unions finden Sie unter [Unions](../cpp/unions.md).\) Anonyme Klassen:  
  
-   Können keinen Konstruktor oder Destruktor aufweisen.  
  
-   Können nicht als Argumente an Funktionen übergeben werden \(es sei denn, die Typüberprüfung wird mithilfe von Ellipsen außer Kraft gesetzt\).  
  
-   Können nicht als Rückgabewerte von Funktionen zurückgegeben werden.  
  
## Anonyme Strukturen  
  
### Microsoft\-spezifisch  
 Eine Microsoft C\-Erweiterung ermöglicht es Ihnen, eine Strukturvariable innerhalb einer anderen Struktur zu deklarieren, ohne ihr einen Namen zu geben.  Diese geschachtelten Strukturen werden als anonyme Strukturen bezeichnet.  In C\+\+ sind anonyme Strukturen nicht zulässig.  
  
 Sie können auf Member einer anonymen Struktur zugreifen, als ob sie Member der enthaltenden Struktur wären.  
  
```  
// anonymous_structures.c  
#include <stdio.h>  
  
struct phone  
{  
    int  areacode;  
    long number;  
};  
  
struct person  
{  
    char   name[30];  
    char   gender;  
    int    age;  
    int    weight;  
    struct phone;    // Anonymous structure; no name needed  
} Jim;  
  
int main()  
{  
    Jim.number = 1234567;  
    printf_s("%d\n", Jim.number);     
}  
//Output: 1234567  
```  
  
### Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [\(NOTINBUILD\) Defining Class Types](assetId:///e8c65425-0f3a-4dca-afc2-418c3b1e57da)