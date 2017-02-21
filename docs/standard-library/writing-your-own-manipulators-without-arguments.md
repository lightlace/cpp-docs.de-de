---
title: "Schreiben eigener Manipulatoren ohne Argumente | Microsoft Docs"
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
  - "Manipulatoren"
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schreiben eigener Manipulatoren ohne Argumente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Schreibenmanipulatoren, die keine Argumente verwenden, erfordert Klassenableitung weder noch Verwendung von komplexen Makros.  Angenommen, das Drucker die Paare \<ESC\>erfordert \[fett Modus eingeben.  Sie können dieses Paar direkt in den Stream einfügen:  
  
```  
cout << "regular " << '\033' << '[' << "boldface" << endl;  
```  
  
 Alternativ können Sie den Manipulator `bold` definieren, der die Zeichen eingefügt wird:  
  
```  
ostream& bold( ostream& os ) {  
    return os << '\033' << '[';  
}  
cout << "regular " << bold << "boldface" << endl;  
```  
  
 Die `bold` global definierte Funktion nimmt ein Verweisargument `ostream` und der `ostream` \- Verweis zurück.  Es ist keine Memberfunktion oder ein Friend, da es keinen Zugriff auf private Klassenelementen erfordert.  Die `bold` verbindet Funktion den Stream, da der Operator `<<` des Streams überladen ist, damit dieser Typ der Funktion, mit einer Deklaration zu akzeptieren angezeigt, die ungefähr folgendermaßen aussieht:  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     
   // call ios_base manipulator  
   (*_Pfn)(*(ios_base *)this);  
   return (*this);  
}  
```  
  
 Sie können diese Funktion verwenden, um andere überladene Operatoren zu erweitern.  In diesem Fall ist jedoch zufällig, dass `bold` Zeichen in den Stream einfügt.  Die Funktion wird, wenn diese in den Stream eingefügt werden, nicht unbedingt aufgerufen, wenn die angrenzenden Zeichen gedruckt werden.  Daher kann das Drucken aufgrund der Pufferung des Streams verzögert werden.  
  
## Siehe auch  
 [Ausgabestreams](../standard-library/output-streams.md)