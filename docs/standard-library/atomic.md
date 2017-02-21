---
title: "&lt;atomic&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<atomic>"
  - "atomic/std::atomic_int_least32_t"
  - "atomic/std::atomic_ullong"
  - "atomic/std::atomic_ptrdiff_t"
  - "atomic/std::atomic_char16_t"
  - "atomic/std::atomic_schar"
  - "atomic/std::atomic_ulong"
  - "atomic/std::atomic_uint_fast32_t"
  - "atomic/std::atomic_uint8_t"
  - "atomic/std::atomic_int32_t"
  - "atomic/std::atomic_uint_fast64_t"
  - "atomic/std::atomic_uint32_t"
  - "atomic/std::atomic_int16_t"
  - "atomic/std::atomic_uintmax_t"
  - "atomic/std::atomic_intmax_t"
  - "atomic/std::atomic_long"
  - "atomic/std::atomic_int"
  - "atomic/std::atomic_uint_least8_t"
  - "atomic/std::atomic_size_t"
  - "atomic/std::atomic_uint_fast16_t"
  - "atomic/std::atomic_wchar_t"
  - "atomic/std::atomic_int_fast64_t"
  - "atomic/std::atomic_uint_fast8_t"
  - "atomic/std::atomic_int_fast8_t"
  - "atomic/std::atomic_intptr_t"
  - "atomic/std::atomic_uint"
  - "atomic/std::atomic_uint16_t"
  - "atomic/std::atomic_char32_t"
  - "atomic/std::atomic_uint64_t"
  - "atomic/std::atomic_ushort"
  - "atomic/std::atomic_int_least16_t"
  - "atomic/std::atomic_char"
  - "atomic/std::atomic_uint_least32_t"
  - "atomic/std::atomic_uintptr_t"
  - "atomic/std::atomic_short"
  - "atomic/std::atomic_llong"
  - "atomic/std::atomic_uint_least16_t"
  - "atomic/std::atomic_int_fast16_t"
  - "atomic/std::atomic_int_least8_t"
  - "atomic/std::atomic_int_least64_t"
  - "atomic/std::atomic_int_fast32_t"
  - "atomic/std::atomic_uchar"
  - "atomic/std::atomic_int8_t"
  - "atomic/std::atomic_int64_t"
  - "atomic/std::atomic_uint_least64_t"
dev_langs: 
  - "C++"
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;atomic&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Klassen und Vorlagenklassen, um zu verwenden, um Typen zu erstellen, die atomare Vorgänge unterstützen.  
  
## Syntax  
  
```cpp  
#include <atomic>  
```  
  
## Hinweise  
  
> [!NOTE]
>  In Code, der kompiliert wird, indem Sie **\/clr** oder **\/clr:pure** verwendet, wird diese Header blockiert.  
  
 Ein atomaren Vorgang verfügt beiden Haupteigenschaften, die Ihnen helfen, mehrere Threads verwenden, um ein Objekt ordnungsgemäß bearbeiten, ohne Mutexsperren zu verwenden.  
  
-   Da atomaren Vorgang unteilbar ist, ein zweiter atomaren Vorgang auf demselben Objekt von einem anderen Thread den Zustand des Objekts vor oder nach dem ersten atomaren Vorgang erhalten.  
  
-   Auf Grundlage [memory\_order](../Topic/memory_order%20Enum.md) sein Argument legt atomaren Vorgang Reihenfolgenanforderungen für die Sichtbarkeit der Effekte anderer atomaren Vorgänge im gleichen Thread ein.  Folglich unterdrückt der Compileroptimierungen, die die Reihenfolgenanforderungen verstoßen.  
  
 Auf einigen Plattformen ist es möglicherweise nicht möglich, von Operationen für Typen eine effiziente implementieren, ohne `mutex` Sperren.  Ein unteilbarer Typ ist *sperrenfrei,* wenn keine atomaren Vorgängen für diese Typen sperrt.  
  
 Die [atomic\_flag](../standard-library/atomic-flag-structure.md) stellt einen minimalen unteilbaren Typ, der ein `bool`\-Flag enthält.  Die Vorgänge sind immer sperrenfrei.  
  
 Die Vorlagenklasse `atomic<Ty>` speichert ein Objekt seinen Argumenttyps `Ty` und bietet Zugriff unteilbaren zu diesem gespeicherten Wert.  Sie können es instanziieren, indem Sie einen Typ verwenden, der, mit dem [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) verwendet und getestet werden kann für Gleichheit kopiert werden, indem Sie [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) verwenden.  Insbesondere können Sie sie mit benutzerdefinierten Typen verwenden, die diese Bedingungen und in vielen Fällen für Gleitkommatypen erfüllen.  
  
 Die Vorlage besitzt auch einen Satz Spezialisierungen für ganzzahlige Typen und teilweise Spezialisierung für Zeiger.  Spezialisierungen Diese stellen zusätzliche Vorgängen, die nicht durch die primäre Vorlage verfügbar sind.  
  
## Zeiger\-Spezialisierungen  
 Die partielle Spezialisierungen `atomic<Ty *>` gelten für alle Zeigertypen zu.  Sie stellen Methoden für Zeigerarithmetik bereit.  
  
## Ganzzahlige Spezialisierungen  
 Die `atomic<integral>` gelten für alle Spezialisierungen ganzzahligen Typen.  Sie stellen zusätzliche Vorgängen, die nicht durch die primäre Vorlage verfügbar sind.  
  
 Jeder Typ `atomic<integral>` verfügt über ein entsprechendes Makro, das Sie in `if directive` verwenden können, um zur Kompilierungszeit nicht feststellen, ob Vorgänge auf diesem Typ sperrenfrei sind.  Wenn der Wert des Makros ist, sind Operationen mit dem Typ nicht sperrenfrei.  Wenn der Wert 1 ist, gestalten sich Operationen sperrenfrei, und könnte die Überprüfung erforderlich.  Wenn der Wert 2 ist, sind sperrenfrei Vorgänge.  Sie können die Funktion `atomic_is_lock_free` verwenden, um zur Laufzeit zu bestimmen, ob Vorgänge auf den Typ sperrenfrei sind.  
  
 Für jeden der ganzzahligen Typen, entspricht ein zugehöriger unteilbaren benannten Typ, der ein Objekt dieses Ganzzahltyp verwaltet.  Jeder Typ `atomic_integral` hat denselben Satz von Memberfunktionen wie die entsprechende Instanziierung von `atomic<Ty>` und kann auf den unteilbaren Funktionen des Nichtmitgliedes übergeben werden.  
  
|`atomic_integral`\-Typ|Ganzzahliger Typ|Makro `atomic_is_lock_free`|  
|----------------------------|----------------------|---------------------------------|  
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|  
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|  
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|  
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|  
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|  
  
 Typedef\-Namen sind für Spezialisierungen der unteilbaren Vorlage für einige der Typen, die in der Headerdatei \<inttypes.h definiert werden.\>  
  
|Unteilbarer Typ|Typedef\-Name|  
|---------------------|-------------------|  
|`atomic_int8_t`|`atomic<int8_t>`|  
|`atomic_uint8_t`|`atomic<uint8_t>`|  
|`atomic_int16_t`|`atomic<int16_t>`|  
|`atomic_uint16_t`|`atomic<uint16_t>`|  
|`atomic_int32_t`|`atomic<int32_t>`|  
|`atomic_uint32_t`|`atomic<uint32_t>`|  
|`atomic_int64_t`|`atomic<int64_t>`|  
|`atomic_uint64_t`|`atomic<uint64_t>`|  
|`atomic_int_least8_t`|`atomic<int_least8_t>`|  
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|  
|`atomic_int_least16_t`|`atomic<int_least16_t>`|  
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|  
|`atomic_int_least32_t`|`atomic<int_least32_t>`|  
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|  
|`atomic_int_least64_t`|`atomic<int_least64_t>`|  
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|  
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|  
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|  
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|  
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|  
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|  
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|  
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|  
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|  
|`atomic_intptr_t`|`atomic<intptr_t>`|  
|`atomic_uintptr_t`|`atomic<uintptr_t>`|  
|`atomic_size_t`|`atomic<size_t>`|  
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|  
|`atomic_intmax_t`|`atomic<intmax_t>`|  
|`atomic_uintmax_t`|`atomic<uintmax_t>`|  
  
## Strukturen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic\-Struktur](../standard-library/atomic-structure.md)|Beschreibt ein Objekt, das von Operationen für einen gespeicherten Wert ausführt.|  
|[atomic\_flag\-Struktur](../standard-library/atomic-flag-structure.md)|Beschreibt ein Objekt, das ein Flag `bool`\-Flag atomisch festlegt und löscht.|  
  
## Enumerationen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[memory\_order\-Enumeration](../Topic/memory_order%20Enum.md)|Stellt symbolische Namen für Synchronisierungsvorgänge auf Speicheradressen bereit.  Diese Vorgänge wirken sich auf das Sichtbarwerden der Zuweisung eines Thread in einem anderen aus.|  
  
## Funktionen  
 In der folgenden Liste werden die Funktionen, die nicht in `_explicit` beenden, die Semantik entsprechenden `_explicit`, außer dass sie haben die impliziten [memory\_order](../Topic/memory_order%20Enum.md)\-Argumente von `memory_order_seq_cst`.  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[atomic\_compare\_exchange\_strong\-Funktion](../Topic/atomic_compare_exchange_strong%20Function.md)|Führt einen *atomischen Vergleichs\- und Austausch*\-Vorgang aus.|  
|[atomic\_compare\_exchange\_strong\_explicit\-Funktion](../Topic/atomic_compare_exchange_strong_explicit%20Function.md)|Führt einen *atomischen Vergleichs\- und Austausch*\-Vorgang aus.|  
|[atomic\_compare\_exchange\_weak\-Funktion](../Topic/atomic_compare_exchange_weak%20Function.md)|Führt einen *schwachen atomischen Vergleichs\- und Austausch*\-Vorgang aus.|  
|[atomic\_compare\_exchange\_weak\_explicit\-Funktion](../Topic/atomic_compare_exchange_weak_explicit%20Function.md)|Führt einen *schwachen atomischen Vergleichs\- und Austausch*\-Vorgang aus.|  
|[atomic\_exchange\-Funktion](../Topic/atomic_exchange%20Function.md)|Ersetzt einen gespeicherten Wert.|  
|[atomic\_exchange\_explicit\-Funktion](../Topic/atomic_exchange_explicit%20Function.md)|Ersetzt einen gespeicherten Wert.|  
|[atomic\_fetch\_add\-Funktion](../Topic/atomic_fetch_add%20Function.md)|Fügt einem angegebenen Wert einem vorhandenen gespeicherten Wert hinzu.|  
|[atomic\_fetch\_add\_explicit\-Funktion](../Topic/atomic_fetch_add_explicit%20Function.md)|Fügt einem angegebenen Wert einem vorhandenen gespeicherten Wert hinzu.|  
|[atomic\_fetch\_and\-Funktion](../Topic/atomic_fetch_and%20Function.md)|Führt eine bitweise `and` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_and\_explicit\-Funktion](../Topic/atomic_fetch_and_explicit%20Function.md)|Führt eine bitweise `and` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_or\-Funktion](../Topic/atomic_fetch_or%20Function.md)|Führt eine bitweise `or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_or\_explicit\-Funktion](../Topic/atomic_fetch_or_explicit%20Function.md)|Führt eine bitweise `or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_sub\-Funktion](../Topic/atomic_fetch_sub%20Function.md)|Subtrahiert einen angegebenen Wert aus einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_sub\_explicit\-Funktion](../Topic/atomic_fetch_sub_explicit%20Function.md)|Subtrahiert einen angegebenen Wert aus einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_xor\-Funktion](../Topic/atomic_fetch_xor%20Function.md)|Führt eine bitweise `exclusive or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_fetch\_xor\_explicit\-Funktion](../Topic/atomic_fetch_xor_explicit%20Function.md)|Führt eine bitweise `exclusive or` auf einem angegebenen Wert und einem vorhandenen gespeicherten Wert.|  
|[atomic\_flag\_clear\-Funktion](../Topic/atomic_flag_clear%20Function.md)|Legt das Flag in einem `atomic_flag`\-Objekt auf `false` fest.|  
|[atomic\_flag\_clear\_explicit\-Funktion](../Topic/atomic_flag_clear_explicit%20Function.md)|Legt das Flag in einem `atomic_flag`\-Objekt auf `false` fest.|  
|[atomic\_flag\_test\_and\_set\-Funktion](../Topic/atomic_flag_test_and_set%20Function.md)|Legt das Flag in einem `atomic_flag`\-Objekt auf `true` fest.|  
|[atomic\_flag\_test\_and\_set\_explicit\-Funktion](../Topic/atomic_flag_test_and_set_explicit%20Function.md)|Legt das Flag in einem `atomic_flag`\-Objekt auf `true` fest.|  
|[atomic\_init\-Funktion](../Topic/atomic_init%20Function.md)|Legt den gespeicherten Wert in einem `atomic`\-Objekt fest.|  
|[atomic\_is\_lock\_free\-Funktion](../Topic/atomic_is_lock_free%20Function.md)|Gibt an, ob von Operationen bei einem angegebenen Objekt sperrenfrei sind.|  
|[atomic\_load\-Funktion](../Topic/atomic_load%20Function.md)|Ruft atomar einen Wert ab.|  
|[atomic\_load\_explicit\-Funktion](../Topic/atomic_load_explicit%20Function.md)|Ruft atomar einen Wert ab.|  
|[atomic\_signal\_fence\-Funktion](../Topic/atomic_signal_fence%20Function.md)|Fungiert als *Zaun auf,* der Arbeitsspeicherreihenfolgenanforderungen zwischen Zäunen in einem aufrufende Thread wird, der die Signalhandler verfügt, die im gleichen Thread ausgeführt werden.|  
|[atomic\_store\-Funktion](../Topic/atomic_store%20Function.md)|Speichert atomar einen Wert.|  
|[atomic\_store\_explicit\-Funktion](../Topic/atomic_store_explicit%20Function.md)|Speichert atomar einen Wert.|  
|[atomic\_thread\_fence\-Funktion](../Topic/atomic_thread_fence%20Function.md)|Fungiert als *Zaun auf,* der Arbeitsspeicherreihenfolgenanforderungen in Bezug auf andere Zäune einrichtet.|  
|[kill\_dependency\-Funktion](../Topic/kill_dependency%20Function.md)|Teilt eine mögliche Abhängigkeitskette.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Standard Template Library](../misc/standard-template-library.md)