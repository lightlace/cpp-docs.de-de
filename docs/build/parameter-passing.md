---
title: "Parameter&#252;bergabe"
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
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Parameter&#252;bergabe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die ersten vier ganzzahligen Argumente werden in Registern übergeben.  Ganzzahlige Werte sind \(in der Reihenfolge von links nach rechts\) in RCX, in RDX, in R8 und in R9 übergeben.  Argumente fünf und höher werden auf dem Stapel übergeben.  Alle Argumente sind in Registern rechtsbündig ausgerichtet.  Dies geschieht, damit der Aufgerufene die oberen Bits des Registers gegebenenfalls ignorieren und nur auf den erforderlichen Teil des Registers zugreifen kann.  
  
 Gleitkomma\-Argumente und Argumente mit doppelter Genauigkeit werden in XMM0 bis XMM3 \(bis 4\) mit dem Ganzzahlslot \(RCX, RDX, R8 und R9\) übergeben, der normalerweise für den ignorierten Hauptslot verwendet würde \(siehe Beispiel\) und umgekehrt.  
  
 [\_\_m128](../cpp/m128.md)\-Typen, Arrays und Zeichenfolgen werden nie von unmittelbaren Wert übergeben, sondern wird ein Zeiger auf den Speicher übergeben, die vom Aufrufer zugeordnet ist.  Strukturen und Unions Größe von 8, 16, 32 oder 64 Bits und der \_\_m64 werden übergeben, als ob sie ganze Zahlen derselben Größe waren.  Strukturen und Unions als diese Größen werden als Zeiger auf den Speicher übergeben, die vom Aufrufer zugeordnet ist.  Der vom Aufrufer belegte temporäre Speicher für diese als Zeiger übergebenen Aggregattypen \(einschließlich \_\_m128\) ist auf 16 Byte ausgerichtet.  
  
 Systeminterne Funktionen, die keinen Stapelspeicher zuweisen und keine anderen Funktionen aufrufen, können andere flüchtige Register für die Übergabe zusätzlicher Registerargumente verwenden, da eine enge Bindung zwischen dem Compiler und der Implementierung der systeminternen Funktion besteht.  Hier bietet sich eine weitere Gelegenheit zur Verbesserung der Leistung.  
  
 Der Aufgerufene hat die Aufgabe, die Registerparameter bei Bedarf in ihrem Shadow\-Speicher zu sichern.  
  
 In der folgenden Tabelle ist zusammengefasst, wie Parameter übergeben werden:  
  
|Parametertyp|Übergabe|  
|------------------|--------------|  
|Gleitkomma|Erste 4 Parameter: XMM0 bis XMM3.  Weitere Parameter werden an den Stapel übergeben.|  
|Ganze Zahl|Erste 4 Parameter: RCX, RDX, R8, R9.  Weitere Parameter werden an den Stapel übergeben.|  
|Aggregate \(8, 16, 32 oder 64 Bits\) und \_\_m64|Erste 4 Parameter: RCX, RDX, R8, R9.  Weitere Parameter werden an den Stapel übergeben.|  
|Aggregate \(sonstige\)|Durch Zeiger.  Die ersten 4 Parameter werden als Zeiger in RCX, RDX, R8 und R9 übergeben.|  
|\_\_m128|Durch Zeiger.  Die ersten 4 Parameter werden als Zeiger in RCX, RDX, R8 und R9 übergeben.|  
  
## Beispiel 1 für die Argumentübergabe: nur ganze Zahlen  
  
```  
func1(int a, int b, int c, int d, int e);    
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack  
```  
  
## Beispiel 2 für die Argumentübergabe: nur Gleitkommazahlen  
  
```  
func2(float a, double b, float c, double d, float e);    
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack  
```  
  
## Beispiel 3 für die Argumentübergabe: Gemischte Ganz\- und Gleitkommazahlen  
  
```  
func3(int a, double b, int c, float d);    
// a in RCX, b in XMM1, c in R8, d in XMM3  
```  
  
## Beispiel 4 für die Argumentübergabe: \_\_m64, \_\_m128 und Aggregate  
  
```  
func4(__m64 a, _m128 b, struct c, float d);  
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3  
```  
  
## Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)