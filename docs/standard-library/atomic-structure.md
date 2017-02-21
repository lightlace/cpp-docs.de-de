---
title: "atomic-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic/std::atomic"
dev_langs: 
  - "C++"
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# atomic-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das auf einem gespeicherten Wert des Typs `Ty` atomische Vorgänge ausführt.  
  
## Syntax  
  
```  
template <class Ty>  
struct atomic;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic::atomic\-Konstruktor](../Topic/atomic::atomic%20Constructor.md)|Erstellt ein atomisches Objekt.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic::operator Ty Operator](../Topic/atomic::operator%20Ty%20Operator.md)|Liest und den gespeicherten Wert und gibt ihn zurück. \([atomic::load\-Methode](../Topic/atomic::load%20Method.md)\)|  
|[atomic::operator\= Operator](../Topic/atomic::operator=%20Operator.md)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert. \([atomic::store\-Methode](../Topic/atomic::store%20Method.md)\)|  
|||  
|[atomic::operator\+\+ Operator](../Topic/atomic::operator++%20Operator.md)|Erhöht den gespeicherten Wert.  Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator\+\= Operator](../Topic/atomic::operator+=%20Operator.md)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.  Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator\-\- Operator](../Topic/atomic::operator--%20Operator.md)|Verringert den gespeicherten Wert.  Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator\-\= Operator](../Topic/atomic::operator-=%20Operator.md)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.  Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator&\= Operator](../Topic/atomic::operator&=%20Operator.md)|Führt ein bitweises `and` auf einem angegebenen Wert und dem gespeicherten Wert aus.  Wird nur bei Integralspezialisierungen verwendet.|  
|[atomic::operator&#124;\= Operator](../Topic/atomic::operator%7C=%20Operator.md)|Führt ein bitweises `or` auf einem angegebenen Wert und dem gespeicherten Wert aus.  Wird nur bei Integralspezialisierungen verwendet.|  
|[atomic::operator^\= Operator](../Topic/atomic::operator%5E=%20Operator.md)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und dem gespeicherten Wert aus.  Wird nur bei Integralspezialisierungen verwendet.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic::compare\_exchange\_strong\-Methode](../Topic/atomic::compare_exchange_strong%20Method.md)|Führt einen `atomic_compare_and_exchange`\-Vorgang auf `this` aus und gibt das Ergebnis zurück.|  
|[atomic::compare\_exchange\_weak\-Methode](../Topic/atomic::compare_exchange_weak%20Method.md)|Führt einen `weak_atomic_compare_and_exchange`\-Vorgang auf `this` aus und gibt das Ergebnis zurück.|  
|[atomic::fetch\_add\-Methode](../Topic/atomic::fetch_add%20Method.md)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.|  
|[atomic::fetch\_and\-Methode](../Topic/atomic::fetch_and%20Method.md)|Führt ein bitweises `and` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[atomic::fetch\_or\-Methode](../Topic/atomic::fetch_or%20Method.md)|Führt ein bitweises `or` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[atomic::fetch\_sub\-Methode](../Topic/atomic::fetch_sub%20Method.md)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.|  
|[atomic::fetch\_xor\-Methode](../Topic/atomic::fetch_xor%20Method.md)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[atomic::is\_lock\_free\-Methode](../Topic/atomic::is_lock_free%20Method.md)|Gibt an, ob die atomischen Vorgänge auf `this`*sperrfrei* sind.  Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.|  
|[atomic::load\-Methode](../Topic/atomic::load%20Method.md)|Liest und den gespeicherten Wert und gibt ihn zurück.|  
|[atomic::store\-Methode](../Topic/atomic::store%20Method.md)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert.|  
  
## Hinweise  
 Der `Ty`\-Typ muss *belanglos kopierbar* sein.  Das heißt, das Kopieren der Bytes mithilfe von [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) muss ein gültiges `Ty`\-Objekt erstellen, das im Vergleich dem ursprünglichen Objekt entspricht.  Bei den Memberfunktionen `compare_exchange_weak` und `compare_exchange_strong` wird [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) verwenden, um zu bestimmen, ob zwei `Ty`\-Werte gleich sind.  Bei diesen Funktionen wird kein `Ty`\-definiertes `operator==` verwendet.  Für die Memberfunktionen von `atomic` wird `memcpy` zum Kopieren der Werte des Typs `Ty` verwendet.  
  
 Eine teilweise Spezialisierung, `atomic<Ty *>`, ist für alle Zeigertypen vorhanden.  Mit der Spezialisierung wird das Hinzufügen eines Offsets zum verwalteten Zeigerwert oder die Wegnahme eines Offsets von dort ermöglicht.  Mit den arithmetischen Operationen wird ein Argument des Typs `ptrdiff_t` akzeptiert und entsprechend der Größe von `Ty` angepasst, damit es mit normaler Adressenarithmetik konsistent ist.  
  
 Eine Spezialisierung ist für jeden Integraltypen außer `bool` vorhanden.  Mit jeder Spezialisierung wird ein umfangreicher Satz an Methoden für atomisch arithmetische und logische Vorgänge bereitgestellt.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Integralspezialisierungen werden von den entsprechenden `atomic_``integral`\-Typen abgeleitet.  So wird `atomic<unsigned int>` z. B. von `atomic_uint` abgeleitet.  
  
## Anforderungen  
 **Header:** atomisch  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<atomic\>](../standard-library/atomic.md)   
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)