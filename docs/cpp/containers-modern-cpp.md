---
title: "Container (Modern C++)"
ms.custom: na
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 6e10b758-e928-4827-9c3f-86cafe54bf5b
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Container (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig verwenden [Vektor](vector%20Class.md) als standardmäßigen sequenziellen Container in C++. Dies ist die Entsprechung von List \< T> in anderen Sprachen.  
  
```cpp  
vector<string> v;  
v.push_back( "Geddy Lee" );  
  
```  
  
 Verwendung [Zuordnung](../standard-library/map-class.md) (nicht Unordered_map) als standardmäßigen assoziativen Container. Verwendung [festgelegt](../standard-library/set-class.md), [mehrfachzuordnung](../standard-library/multimap-class.md), [Multimenge](../standard-library/multiset-class.md) für degenerierte & mehrfachfälle.  
  
```cpp  
map<string, string> phone_book;  
// ...  
phone_book["Alex Lifeson"] = "+1 (416) 555-1212";  
  
```  
  
 Wenn eine Leistungsoptimierung erforderlich ist, erwägen Sie folgende Verwendungen:  
  
1.  den Arraytyp, wenn das Einbetten wichtig ist – beispielsweise als Klassenmember.  
  
2.  Ungeordnete assoziative Container (unordered_map, et al.): Niedrigerer Mehraufwand pro Element (Hauptversion) und konstante Zeitsuche (möglicherweise Hauptversion, manchmal Nebenversion). Aufgrund von Unannehmlichkeiten und scharfen Kanten ist die korrekte und effiziente Verwendung schwieriger.  
  
3.  Sortierter Vektor. (Siehe: [Algorithmen](../cpp/algorithms-modern-cpp.md).)  
  
 Verwenden Sie keine C-Arrays. (Verwenden Sie `f( vec.data(), vec.size() );` für ältere APIs.)  
  
 Einen anderen Artikeln zu Containern finden Sie unter [STL-Containern](../standard-library/stl-containers.md).  
  
## <a name="container-sizes"></a>Containergrößen  
 Die folgenden Tabellen zeigen die Containergrößen in Bytes für die x86- und die x64-Plattform an.  (32-Bit-ARM ist in diesen Fällen äquivalent zu x86.)  Diese Tabellen beziehen sich auf den Releasemodus, weil der Debugmodus Überprüfungsmechanismen enthält, die Platz und Zeit benötigen.  Die separaten Spalten sind für [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] SP1, mit dem Standardwert 1 für `_SECURE_SCL`, und [!INCLUDE[cpp_orcas_long](../cpp/includes/cpp_orcas_long_md.md)] SP1, wobei `_SECURE_SCL` manuell auf 0 für Höchstgeschwindigkeit eingestellt wurde.  Visual C++ in Visual Studio 2010, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] und [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] ist `_SECURE_SCL` standardmäßig 0 (jetzt als `_ITERATOR_DEBUG_LEVEL` bezeichnet).  
  
|x86-Containergrößen (Bytes)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|Vector \< Int>|24|16|16|12|  
|array\<int, 5>|20|20|20|20|  
|Deque \< Int>|32|32|24|20|  
|Forward_list \< Int>|Nicht zutreffend|Nicht zutreffend|8|4|  
|Liste \< Int>|28|12|12|8|  
|Priority_queue \< Int>|28|20|20|16|  
|Warteschlange \< Int>|32|32|24|20|  
|Stack \< Int>|32|32|24|20|  
|pair\<int, int>|8|8|8|8|  
|tuple\<int, int, int>|16|16|16|12|  
|map\<int, int>|32|12|16|8|  
|multimap\<int, int>|32|12|16|8|  
|Legen Sie \< Int>|32|12|16|8|  
|Multiset \< Int>|32|12|16|8|  
|hash_map\<int, int>|72|44|44|32|  
|hash_multimap\<int, int>|72|44|44|32|  
|Hash_set \< Int>|72|44|44|32|  
|Hash_multiset \< Int>|72|44|44|32|  
|unordered_map\<int, int>|72|44|44|32|  
|unordered_multimap\<int, int>|72|44|44|32|  
|unordered_set-Element \< Int>|72|44|44|32|  
Ordered_multiset \< Int>|72|44|44|32|  
|string|28|28|28|24|  
|wstring|28|28|28|24|  
  
|x64-Containergrößen (Bytes)|VC9 SP1|VC9 SP1<br /><br /> SCL=0|VC10|VC11|  
|-----------------------------------|-------------|------------------------|----------|----------|  
|Vector \< Int>|48|32|32|24|  
|array\<int, 5>|20|20|20|20|  
|Deque \< Int>|64|64|48|40|  
|Forward_list \< Int>|Nicht zutreffend|Nicht zutreffend|16|8|  
|Liste \< Int>|56|24|24|16|  
|Priority_queue \< Int>|56|40|40|32|  
|Warteschlange \< Int>|64|64|48|40|  
|Stack \< Int>|64|64|48|40|  
|pair\<int, int>|8|8|8|8|  
|tuple\<int, int, int>|16|16|16|12|  
|map\<int, int>|64|24|32|16|  
|multimap\<int, int>|64|24|32|16|  
|Legen Sie \< Int>|64|24|32|16|  
|Multiset \< Int>|64|24|32|16|  
|hash_map\<int, int>|144|88|88|64|  
|hash_multimap\<int, int>|144|88|88|64|  
|Hash_set \< Int>|144|88|88|64|  
|Hash_multiset \< Int>|144|88|88|64|  
|unordered_map\<int, int>|144|88|88|64|  
|unordered_multimap\<int, int>|144|88|88|64|  
|unordered_set-Element \< Int>|144|88|88|64|  
Ordered_multiset \< Int>|144|88|88|64|  
|string|40|40|40|32|  
|wstring|40|40|40|32|  
  
## <a name="see-also"></a>Siehe auch  
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)