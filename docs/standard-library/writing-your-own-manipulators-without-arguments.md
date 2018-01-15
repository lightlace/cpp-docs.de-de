---
title: Schreiben eigener Manipulatoren ohne Argumente | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: manipulators
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7439908970d61f55f10915ff69bc990a6fcc841
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="writing-your-own-manipulators-without-arguments"></a>Schreiben eigener Manipulatoren ohne Argumente
Das Schreiben von Manipulatoren, die keine Argumente verwenden, erfordert weder eine Klassenableitung noch die Verwendung von komplexen Makros. Angenommen, Ihr Drucker erfordert das Paar \<ESC>[, um in den Fettdruckmodus zu wechseln. Sie können dieses Paar direkt in den Stream einfügen:  
  
```  
cout <<"regular " <<'\033' <<'[' <<"boldface" <<endl;  
```  
  
 Oder Sie können den `bold`-Manipulator definieren, der die Zeichen eingefügt:  
  
```  
ostream& bold(ostream& os) {  
    return os <<'\033' <<'[';  
}  
cout <<"regular " <<bold <<"boldface" <<endl;  
```  
  
 Die global definierte `bold`-Funktion nimmt ein `ostream`-Verweisargument und gibt den `ostream`-Verweis zurück. Dabei handelt es sich um keine Member- oder Friend-Funktion, da kein Zugriff auf private Klassenelemente benötigt wird. Die `bold`-Funktion stellt eine Verbindung mit dem Stream her, da der `<<`-Operator des Streams überladen ist, um diesen Typ von Funktion zu akzeptieren, wobei eine Deklaration verwendet wird, die in etwa wie folgt aussieht:  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     // call ios_base manipulator  
 (*_Pfn)(*(ios_base *)this);

    return (*this);

}  
```  
  
 Sie können diese Funktion verwenden, um andere überladene Operatoren zu erweitern. In diesem Fall fügt `bold` in der Folge Zeichen in den Stream ein. Die Funktion wird aufgerufen, wenn sie in den Stream eingefügt wird, nicht zwangsläufig beim Drucken der angrenzenden Zeichen. Folglich könnte es aufgrund der Streampufferung beim Drucken zu Verzögerungen kommen.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)

