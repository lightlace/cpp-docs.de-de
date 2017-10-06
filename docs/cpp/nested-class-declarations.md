---
title: Geschachtelte Klassendeklarationen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], declaring
- declarations, class
- nested classes [C++]
- nested classes [C++], declaring
- declaring classes [C++]
- declarations, nested classes
ms.assetid: c02e471d-b7f9-41b8-8ef6-2323f006dbd5
caps.latest.revision: 9
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
ms.openlocfilehash: c66636f2780e15df83d016b604f78adae7b62143
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="nested-class-declarations"></a>Geschachtelte Klassendeklarationen
Eine Klasse kann im Bereich einer anderen Klasse deklariert werden. Eine solche Klasse wird als "geschachtelte Klasse" bezeichnet. Geschachtelte Klassen gelten als innerhalb des Bereichs der einschließenden Klasse befindlich und sind für die Verwendung innerhalb dieses Bereichs verfügbar. Um auf eine geschachtelte Klasse aus einem anderen als dem unmittelbar einschließenden Bereich zu verweisen, müssen Sie einen vollqualifizierten Namen angeben.  
  
 Im folgenden Beispiel wird das Deklarieren geschachtelter Klassen veranschaulicht:  
  
```  
// nested_class_declarations.cpp  
class BufferedIO  
{  
public:  
   enum IOError { None, Access, General };  
  
   // Declare nested class BufferedInput.  
   class BufferedInput  
   {  
   public:  
      int read();  
      int good()  
      {  
         return _inputerror == None;  
      }  
   private:  
       IOError _inputerror;  
   };  
  
   // Declare nested class BufferedOutput.  
   class BufferedOutput  
   {  
      // Member list  
   };  
};  
  
int main()  
{  
}  
```  
  
 `BufferedIO::BufferedInput` und `BufferedIO::BufferedOutput` werden innerhalb `BufferedIO` deklariert. Diese Klassennamen sind außerhalb des gültigen Bereichs der Klasse `BufferedIO` nicht sichtbar. Ein Objekt vom Typ `BufferedIO` enthält jedoch keine Objekte des Typs `BufferedInput` oder `BufferedOutput`.  
  
 Geschachtelte Klassen können Namen, Typnamen, Namen statischer Member und Enumeratoren nur aus der einschließenden Klasse direkt verwenden. Um Namen von anderen Klassenmembern zu verwenden, müssen Sie Zeiger, Verweise oder Objektnamen verwenden.  
  
 Im vorherigen Beispiel mit `BufferedIO` kann auf die Enumeration `IOError` direkt von Memberfunktionen in den geschachtelten Klassen `BufferedIO::BufferedInput` oder `BufferedIO::BufferedOutput` zugegriffen werden, wie in der `good`-Funktion gezeigt wird.  
  
> [!NOTE]
>  Geschachtelte Klassen deklarieren nur Typen innerhalb des gültigen Klassenbereichs. Sie führen nicht dazu, dass enthaltene Objekte der geschachtelten Klasse erstellt werden. Das vorhergehende Beispiel deklariert zwei geschachtelte Klassen, jedoch keine Objekte dieser Klassentypen.  
  
 Eine Ausnahme von der Bereichssichtbarkeit einer Deklaration der geschachtelten Klasse ist, wenn ein Typname zusammen mit einer Vorwärtsdeklaration deklariert ist.  In diesem Fall ist der Klassenname, der von der Vorwärtsdeklaration deklariert wird, außerhalb der einschließenden Klasse sichtbar, wobei sein Bereich als kleinster einschließender Nichtklassenbereich definiert wird.  Zum Beispiel:  
  
```  
// nested_class_declarations_2.cpp  
class C  
{  
public:  
    typedef class U u_t; // class U visible outside class C scope  
    typedef class V {} v_t; // class V not visible outside class C  
};  
  
int main()  
{  
    // okay, forward declaration used above so file scope is used  
    U* pu;  
  
    // error, type name only exists in class C scope  
    u_t* pu2; // C2065  
  
    // error, class defined above so class C scope  
    V* pv; // C2065  
  
    // okay, fully qualified name  
    C::V* pv2;  
}  
```  
  
## <a name="access-privilege-in-nested-classes"></a>Zugriffsrecht in geschachtelten Klassen  
 Das Schachteln einer Klasse in einer anderen Klasse gewährt keine speziellen Zugriffsrechte auf die Memberfunktionen der geschachtelten Klasse. Ebenso bieten Memberfunktionen der einschließenden Klasse keinen speziellen Zugriff auf die Member der geschachtelten Klasse.  
  
## <a name="member-functions-in-nested-classes"></a>Memberfunktionen in geschachtelten Klassen  
 Die Memberfunktionen, die in den geschachtelten Klassen deklariert werden, können im Dateibereich definiert werden. Das vorhergehende Beispiel könnte so aussehen:  
  
```  
// member_functions_in_nested_classes.cpp  
class BufferedIO  
{  
public:  
    enum IOError { None, Access, General };  
    class BufferedInput  
    {  
    public:  
        int read(); // Declare but do not define member  
        int good(); //  functions read and good.  
    private:  
        IOError _inputerror;  
    };  
  
    class BufferedOutput  
    {  
        // Member list.  
    };  
};  
// Define member functions read and good in  
//  file scope.  
int BufferedIO::BufferedInput::read()  
{  
   return(1);  
}  
  
int BufferedIO::BufferedInput::good()  
{  
    return _inputerror == None;  
}  
int main()  
{  
}  
```  
  
 Im vorherigen Beispiel der *qualified-Type-Name* Syntax wird verwendet, um den Namen der Funktion zu deklarieren. Die Deklaration:  
  
```  
BufferedIO::BufferedInput::read()  
```  
  
 bedeutet "die `read`-Funktion, die ein Member der `BufferedInput`-Klasse ist, die im Bereich der `BufferedIO`-Klasse liegt". Da diese Deklaration verwendet die *qualified-Type-Name* Syntax Konstrukte der folgenden Form sind möglich:  
  
```  
typedef BufferedIO::BufferedInput BIO_INPUT;  
  
int BIO_INPUT::read()  
```  
  
 Die vorhergehende Deklaration entspricht der vorherigen, aber sie verwendet einen `typedef`-Namen anstelle von Klassennamen.  
  
## <a name="friend-functions-in-nested-classes"></a>Friend-Funktionen in geschachtelten Klassen  
 Die friend-Funktionen, die in einer geschachtelten Klasse deklariert werden, gelten als zum Bereich der geschachtelten Klasse zugehörig, nicht der einschließenden Klasse. Daher erhalten die friend-Funktionen keine besonderen Zugriffsrechte auf Member oder Memberfunktionen der einschließenden Klasse. Wenn Sie einen Namen verwenden möchten, der in einer geschachtelten Klasse in einer friend-Funktion deklariert ist, und diese friend-Funktion im Dateibereich definiert ist, verwenden Sie qualifizierte Typnamen wie folgt:  
  
```  
// friend_functions_and_nested_classes.cpp  
  
#include <string.h>  
  
enum  
{  
    sizeOfMessage = 255  
};  
  
char *rgszMessage[sizeOfMessage];  
  
class BufferedIO  
{  
public:  
    class BufferedInput  
    {  
    public:  
        friend int GetExtendedErrorStatus();  
        static char *message;  
        static int  messageSize;  
        int iMsgNo;  
   };  
};  
  
char *BufferedIO::BufferedInput::message;  
int BufferedIO::BufferedInput::messageSize;  
  
int GetExtendedErrorStatus()  
{  
    int iMsgNo = 1; // assign arbitrary value as message number  
  
    strcpy_s( BufferedIO::BufferedInput::message,  
              BufferedIO::BufferedInput::messageSize,  
              rgszMessage[iMsgNo] );  
  
    return iMsgNo;  
}  
  
int main()  
{  
}  
```  
  
 Der folgende Code zeigt die Funktion `GetExtendedErrorStatus` als friend-Funktion deklariert. In der Funktion, die im Dateibereich definiert ist, wird eine Nachricht von einem statischen Array in einen Klassenmember kopiert. Beachten Sie, dass eine bessere Implementierung von `GetExtendedErrorStatus` erfolgt, wenn dies wie folgt deklariert wird:  
  
```  
int GetExtendedErrorStatus( char *message )  
```  
  
 Bei der vorherigen Schnittstelle können mehrere Klassen die Dienste dieser Funktion verwenden, indem eine Speicheradresse übergeben wird, an welche die Fehlermeldung kopiert werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../cpp/classes-and-structs-cpp.md)
