---
title: "Änderungen bei Konvertierungsoperatoren | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- conversion operators
- operators [C++], explicit type conversion
- type conversion, explicit conversions
- conversions, explicit
- explicit keyword [C++]
ms.assetid: 9b83925c-71b7-4bd3-ac2e-843dd7c7f184
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8f89c49035e2e48dde8d502b1d61fa33d198f69a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changes-to-conversion-operators"></a>Änderungen bei Konvertierungsoperatoren
Die Syntax für Konvertierungsoperatoren hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 Ein Beispiel für besteht darin zu schreiben `op_Implicit` eine Konvertierung angeben. Hier ist eine Definition der `MyDouble` der Sprachspezifikation entnommen:  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 Das bedeutet, dass der Algorithmus zum Konvertieren von ganzen Zahl in eine ganze Zahl angegeben ein `MyDouble` wird bereitgestellt, indem Sie die `op_Implicit` Operator. Darüber hinaus wird diese Konvertierung implizit vom Compiler ausgeführt werden. Auf ähnliche Weise erhält eine `MyDouble` -Objekt, das zwei `op_Explicit` Operatoren geben Sie die jeweiligen Algorithmen zum Konvertieren dieses Objekts in eine ganze Zahl oder einen verwalteten `String` Entität. Allerdings wird der Compiler die Konvertierung nicht ausführen, es sei denn, Sie explizit vom Benutzer angefordert.  
  
 In c# sieht dies wie folgt:  
  
```  
class MyDouble {  
   public static implicit operator MyDouble( int i );   
   public static explicit operator int( MyDouble val );  
   public static explicit operator string( MyDouble val );   
};  
```  
  
 C#-Code sieht C++ mehr aus, als Managed Extensions for C++ ist. Also nicht der Fall, in der neuen Syntax.  
  
 Die ISO-C++-Committee eingeführt, ein Schlüsselwort, `explicit`, gemindert werden kann unbeabsichtigte Folgen – z. B. ein `Array` Klasse, die ein einzelnes ganzzahliges Argument akzeptiert, wie eine beliebige ganze Zahl in eine Dimension implizit konvertiert ein `Array` -Objekt, das ist Sie nicht wünschen. Eine Möglichkeit, dies zu verhindern ist ein Entwurf-Idiom dummy zweites Argument an einen Konstruktor  
  
 Andererseits, sollten Sie ein Konvertierungspaar nicht bereitstellen, beim Entwerfen eines Klassentyps in C++. Das beste Beispiel für diese ist die Standardzeichenfolge-Klasse. Die implizite Konvertierung ist die Einzelargumentkonstruktor übernimmt eine Zeichenfolge im C-Format. Allerdings es bietet keine entsprechenden implizite Konvertierungsoperator -, der Konvertierung einer Zeichenfolge, die Sie Objekt in eine Zeichenfolge im C-Format, sondern stattdessen muss der Benutzer eine benannte Funktion – in diesem Fall explizit aufrufen, um `c_str()`.  
  
 Eine Verbesserung gegenüber dem ursprünglichen C++-Unterstützung für Konvertierungsoperatoren, die schließlich zu den geführthat,werdendaherscheintZuordnenvonimplizitem/explizitemVerhalteneinesKonvertierungsoperators(undwiedieKapselungvonKonvertierungenineineeinzigeDeklaration)`explicit` Schlüsselwort. Die Visual C++-sprachunterstützung für Konvertierungsoperatoren sieht wie folgt aufgrund das Standardverhalten des Operators, der eine implizite Konvertierungsalgorithmus-Anwendung etwas weniger aufwändig als die von c# ist:  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 Eine andere Änderung ist, dass ein Einzelargumentkonstruktor behandelt wird, als ob er als deklariert wird `explicit`. Dies bedeutet, dass damit seine Aufrufe auszulösen, eine explizite Umwandlung erforderlich ist. Beachten Sie jedoch, dass wenn ein explizite Konvertierungsoperator definiert ist, er und nicht die Einzelargumentkonstruktor, aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)