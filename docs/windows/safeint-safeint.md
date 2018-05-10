---
title: 'SafeInt:: SafeInt | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7154349105c1953ad314b7928e7be8385179c42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
Erstellt ein `SafeInt`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `i`  
 Der Wert für die neue `SafeInt` Objekt. Diese Angabe muss einen Parameter vom Typ "T" oder "U, abhängig vom Konstruktor.  
  
 [in] `b`  
 Der boolesche Wert für die neue `SafeInt` Objekt.  
  
 [in] `u`  
 Ein `SafeInt` Typ u. Die neue `SafeInt` -Objekt verfügt insgesamt über den gleichen Wert wie `u`, jedoch vom Typ T.  
  
 U  
 Der Typ der Daten in der `SafeInt`. Dies kann vom Typ Boolesch, Zeichen oder ganze Zahl sein. Wenn es ein Ganzzahltyp ist, es kann sein mit oder ohne Vorzeichen zwischen 8 und 64-Bit.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den Vorlagentypen `T` und `E`, finden Sie unter [SafeInt-Klasse](../windows/safeint-class.md).  
  
 Der input-Parameter des Konstruktors `i` oder `u`, muss vom Typ Boolean, Zeichen oder ganze Zahl sein. Wenn es sich um einen anderen Typ des Parameters, ist die `SafeInt` -Klasse ruft [Static_assert](../cpp/static-assert.md) an, dass ein ungültiger Eingabeparameter.  
  
 Die Konstruktoren, die den Vorlagentyp verwenden `U` automatisch in den vom angegebenen Typ konvertieren den Eingabeparameter `T`. Die `SafeInt` Klasse konvertiert die Daten ohne Verlust von Daten. Er meldet an den Fehlerhandler `E` , wenn sie die Daten in den Typ konvertieren kann `T` ohne Datenverlust.  
  
 Wenn Sie erstellen eine `SafeInt` aus einem booleschen Parameter müssen Sie den Wert sofort initialisiert werden. Sie können nicht erstellt werden ein `SafeInt` mithilfe des Codes `SafeInt<bool> sb;`. Dadurch wird einen Compilerfehler generiert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Siehe auch  
 [SafeInt-Bibliothek](../windows/safeint-library.md)   
 [SafeInt-Klasse](../windows/safeint-class.md)   
 [SafeIntException-Klasse](../windows/safeintexception-class.md)