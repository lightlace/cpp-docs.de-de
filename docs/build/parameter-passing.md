---
title: "Übergeben von Parametern | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0359a6cbbb1f646432b03722cdf4ba3010cffa72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="parameter-passing"></a>Parameterübergabe
Die ersten vier Ganzzahlargumente sind in Registern zu übergeben. Ganzzahlige Werte werden (in der Reihenfolge von links nach rechts) in RCX, RDX, R8 oder R9 übergeben. Argumente 5 und höher auf dem Stapel übergeben werden. Sind alle Argumente in Registern rechts ausgerichtet. Dies erfolgt, d. h. der aufgerufene die höherwertigen Bits des Registers Wenn ignorieren werden müssen und nur den Teil der erforderlichen Register zugreifen können.  
  
 Gleitkomma und doppelter Genauigkeit Argumente übergeben werden, in XMM0: XMM3 (bis zu 4) mit den Integer-Slot (RCX, RDX, R8 und R9), die für diese cardinal Slot wird normalerweise verwendet wird, ignoriert (siehe Beispiel) und umgekehrt.  
  
 [__m128](../cpp/m128.md) Typen, Arrays und Zeichenfolgen nie sofort Wert übergeben werden, aber stattdessen wird ein Zeiger auf vom Aufrufer zugeordneten Speicher übergeben. Strukturen oder Unions von Größe 8, 16, 32 oder 64 Bits und __m64 werden übergeben, als wären sie ganze Zahlen mit derselben Größe zu. Strukturen oder Unions, als diese Größen werden als Zeiger auf vom Aufrufer zugeordneten Speicher übergeben. Übergeben Sie für diese Aggregattypen als Zeiger (einschließlich \__m128), die vom Aufrufer reservierten temporäre Speicher werden 16-Byte-ausgerichtet.  
  
 Intrinsische Funktionen, die Stapelspeicher nicht reservieren und rufen Sie keine anderen Funktionen können andere flüchtige Register zusätzliche Registerargumente übergeben werden, da eine enge Bindung zwischen dem Compiler und die Implementierung der systeminternen Funktion vorhanden ist. Dies ist eine weitere Möglichkeit zum Verbessern der Leistung.  
  
 Die aufgerufene Methode ist dafür verantwortlich, die Registerparameter in der Schattenkopie-Speicherplatz bei Bedarf Dump-Sicherungen.  
  
 Die folgende Tabelle fasst zusammen, wie Parameter übergeben werden:  
  
|Parametertyp|Wie übergebene|  
|--------------------|----------------|  
|Gleitkomma|Erste 4 Parameter - XMM0 bis XMM3. Andere Benutzer übergeben an den Stapel.|  
|Ganze Zahl|Erste 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|  
|Aggregate (8, 16, 32 oder 64-Bit) und __m64|Erste 4 Parameter – RCX, RDX, R8 R9. Andere Benutzer übergeben an den Stapel.|  
|Aggregate (andere)|Der vom Zeiger. Erste 4 Parameter als Zeiger in RCX, RDX, R8 oder R9 übergeben|  
|__m128|Der vom Zeiger. Erste 4 Parameter als Zeiger in RCX, RDX, R8 oder R9 übergeben|  
  
## <a name="example-of-argument-passing-1---all-integers"></a>Beispiel 1 – alle ganzen Zahlen für die Argumentübergabe  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-2---all-floats"></a>Beispiel 2 – alle Gleitkommazahlen für die Argumentübergabe  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Beispiel 3 – gemischte ganz- und Gleitkommazahlen für die Argumentübergabe  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Beispiel für die Argumentübergabe 4-__m64, \__m128, und Aggregate  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)