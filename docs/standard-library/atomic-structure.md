---
title: atomic-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: fd21d2fe59dc7db7670fb94fde6d169603bbf6d1
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="atomic-structure"></a>atomic-Struktur
Beschreibt ein Objekt, das auf einem gespeicherten Wert des Typs `Ty` atomische Vorgänge ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Ty>
struct atomic;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[atomic](http://msdn.microsoft.com/Library/a538c43f-4d48-4308-ae1b-bab1839bccb8)|Erstellt ein atomisches Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[atomic::operator Ty-Operator](http://msdn.microsoft.com/Library/a366c700-c7a0-4bcb-8eb4-4b57dfaea065)|Liest und den gespeicherten Wert und gibt ihn zurück. ([Atomic:: Load](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1))|  
|[atomic::operator=-Operator](http://msdn.microsoft.com/Library/fe161d57-47ae-4bad-92bf-ce32ac8d5953)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert. ([Atomic:: Store](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b))|  
|[atomic::operator++-Operator](http://msdn.microsoft.com/Library/492959e9-1ea8-4e02-a031-82b1b92e91a0)|Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator+=-Operator](http://msdn.microsoft.com/Library/9ec97aa2-c9d7-436b-943d-2989eb2617dd)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu. Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator---Operator](http://msdn.microsoft.com/Library/ad7c1ea7-1f6d-4a54-bf26-07630f749864)|Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator-=-Operator](http://msdn.microsoft.com/Library/902d0d9f-88fd-4500-aa2d-1e50f443e77c)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|  
|[atomic::operator&=-Operator](http://msdn.microsoft.com/Library/90e730ac-12e1-4abb-98f5-4eadd6861a89)|Führt ein bitweises `and` auf einem angegebenen Wert und dem gespeicherten Wert aus. Wird nur bei Integralspezialisierungen verwendet.|  
|[atomic::operator&#124;=-Operator](http://msdn.microsoft.com/Library/f105eacc-31a6-4906-abba-f1cf013599b2)|Führt ein bitweises `or` auf einem angegebenen Wert und dem gespeicherten Wert aus. Wird nur bei Integralspezialisierungen verwendet.|  
|[atomic::operator^=-Operator](http://msdn.microsoft.com/Library/f2a4da9d-67e8-4249-9161-9998e72a33c2)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und dem gespeicherten Wert aus. Wird nur bei Integralspezialisierungen verwendet.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[compare_exchange_strong](http://msdn.microsoft.com/Library/47bbf894-b28c-4ece-959e-67b3863cf4ed)|Führt einen `atomic_compare_and_exchange`-Vorgang auf `this` aus und gibt das Ergebnis zurück.|  
|[compare_exchange_weak](http://msdn.microsoft.com/Library/e15e421a-f7a3-4272-993a-f487d2242e4f)|Führt einen `weak_atomic_compare_and_exchange`-Vorgang auf `this` aus und gibt das Ergebnis zurück.|  
|[fetch_add](http://msdn.microsoft.com/Library/c68b91f2-6e8a-4ffa-8991-6bb6d466e1f3)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.|  
|[fetch_and](http://msdn.microsoft.com/Library/a9c83001-b72c-4085-9640-f63f866714b9)|Führt ein bitweises `and` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[fetch_or](http://msdn.microsoft.com/Library/4c532f7f-80c5-432a-b34b-48feacab8dca)|Führt ein bitweises `or` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[fetch_sub](http://msdn.microsoft.com/Library/8cc80d4b-0942-45a3-9db8-bbf339a903e4)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.|  
|[fetch_xor](http://msdn.microsoft.com/Library/92bbaff8-ee29-4a1e-aee4-d9d405285bfe)|Führt ein bitweises `exclusive or` auf einem angegebenen Wert und dem gespeicherten Wert aus.|  
|[is_lock_free](http://msdn.microsoft.com/Library/b99d5130-cdda-40a2-b14c-152b13a8ba45)|Gibt an, ob die atomischen Vorgänge auf `this` *sperrfrei* sind. Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.|  
|[Laden](http://msdn.microsoft.com/Library/05212726-cf8a-46fe-83d2-c16ac2abb7d1)|Liest und den gespeicherten Wert und gibt ihn zurück.|  
|[Speichern](http://msdn.microsoft.com/Library/84759413-d664-47ef-a1f3-a73c5a62007b)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert.|  
  
## <a name="remarks"></a>Hinweise  
 Der `Ty`-Typ muss *einfach kopierbar* sein. Das heißt, das Kopieren der Bytes mithilfe von [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) muss ein gültiges `Ty`-Objekt erstellen, das im Vergleich dem ursprünglichen Objekt entspricht. Bei den Memberfunktionen `compare_exchange_weak` und `compare_exchange_strong` wird [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) verwendet, um zu bestimmen, ob zwei `Ty`-Werte gleich sind. Bei diesen Funktionen wird kein `Ty`-definiertes `operator==` verwendet. Für die Memberfunktionen von `atomic` wird `memcpy` zum Kopieren der Werte des Typs `Ty` verwendet.  
  
 Eine teilweise Spezialisierung, `atomic<Ty *>`, ist für alle Zeigertypen vorhanden. Mit der Spezialisierung wird das Hinzufügen eines Offsets zum verwalteten Zeigerwert oder die Wegnahme eines Offsets von dort ermöglicht. Mit den arithmetischen Operationen wird ein Argument des Typs `ptrdiff_t` akzeptiert und entsprechend der Größe von `Ty` angepasst, damit es mit normaler Adressenarithmetik konsistent ist.  
  
 Eine Spezialisierung ist für jeden Integraltypen außer `bool` vorhanden. Mit jeder Spezialisierung wird ein umfangreicher Satz an Methoden für atomisch arithmetische und logische Vorgänge bereitgestellt.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 Integralspezialisierungen werden von den entsprechenden `atomic_``integral`-Typen abgeleitet. So wird `atomic<unsigned int>` z. B. von `atomic_uint` abgeleitet.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<atomic >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<atomic>](../standard-library/atomic.md)   
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)




