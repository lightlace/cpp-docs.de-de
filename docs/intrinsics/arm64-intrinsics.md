---
title: Intrinsie ARM64
description: Eine Liste der ARM64-systeminternen Funktionen, die vom C++ Microsoft-Compiler unterstützt werden.
f1_keywords:
- __break
- __addx18byte
- __addx18word
- __addx18dword
- __addx18qword
- __cas8
- __cas16
- __cas32
- __cas64
- __casa8
- __casa16
- __casa32
- __casa64
- __casl8
- __casl16
- __casl32
- __casl64
- __casal8
- __casal16
- __casal32
- __casal64
- __crc32b
- __crc32h
- __crc32w
- __crc32d
- __crc32cb
- __crc32ch
- __crc32cw
- __crc32cd
- __getReg
- __getRegFp
- __getCallerReg
- __getCallerRegFp
- __hlt
- __incx18byte
- __incx18word
- __incx18dword
- __incx18qword
- __ldar8
- __ldar16
- __ldar32
- __ldar64
- __ldapr8
- __ldapr16
- __ldapr32
- __ldapr64
- __prefetch2
- __readx18byte
- __readx18word
- __readx18dword
- __readx18qword
- __setReg
- __setRegFp
- __setCallerReg
- __setCallerRegFp
- __stlr8
- __stlr16
- __stlr32
- __stlr64
- __swp8
- __swp16
- __swp32
- __swp64
- __swpa8
- __swpa16
- __swpa32
- __swpa64
- __swpl8
- __swpl16
- __swpl32
- __swpl64
- __swpal8
- __swpal16
- __swpal32
- __swpal64
- __sys
- __svc
- __writex18byte
- __writex18word
- __writex18dword
- __writex18qword
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 30881c2b45714f91bf9035819b11ae41322b7086
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163682"
---
# <a name="arm64-intrinsics"></a>Intrinsie ARM64

Der Microsoft C++ -Compiler (MSVC) stellt die folgenden systeminternen Funktionen in der ARM64-Architektur zur Verfügung. Weitere Informationen zu arm finden Sie in den Abschnitten zu Architektur-und Software Entwicklungs Tools der Website für die [Arm-Entwicklerdokumentation](https://developer.arm.com/docs) .

## <a name="top"></a>Far

Die Neon Vector-Anweisungs Satz Erweiterungen für ARM64 stellen Single Instruction Multiple Data Funktionen (SIMD) bereit. Sie ähneln denen in den MMX-und SSE-Vektor Anweisungs Sätzen, die von x86-und x64-Architektur Prozessoren gemeinsam verwendet werden.

Systeminterne Neon-Funktionen werden unterstützt, wie in der Header Datei *arm64_neon. h*bereitgestellt. Die MSVC-Unterstützung für systeminterne Neon-Funktionen ähnelt der des ARM64-Compilers, der in der systeminternen [Referenz zu arm-Neon](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf) auf der Arm-InfoCenter-Website dokumentiert ist.

##  <a name="A"></a>ARM64-spezifische intrinsie-Auflistungen

|Funktionsname|Anweisung|Funktionsprototyp|
|-------------------|-----------------|------------------------|
|__break|BRK|void-__break (int)|
|__addx18byte||void-__addx18byte (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen Char)|
|__addx18word||void-__addx18word (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen Short)|
|__addx18dword||void-__addx18dword (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen long)|
|__addx18qword||void-__addx18qword (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen __int64)|
|__cas8|CASB|nicht signierte __int8 __cas8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Comp, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__cas16|Kassieren|nicht signierte __int16 __cas16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Comp, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__cas32|CAS|nicht signierte __int32 __cas32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Comp, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__cas64|CAS|nicht signierte __int64 __cas64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Comp, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__casa8|Casab|nicht signierte __int8 __casa8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Comp, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__casa16|Casah|nicht signierte __int16 __casa16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Comp, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__casa32|Casa|nicht signierte __int32 __casa32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Comp, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__casa64|Casa|nicht signierte __int64 __casa64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Comp, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__casl8|Caslb|nicht signierte __int8 __casl8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Comp, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__casl16|Caslh|nicht signierte __int16 __casl16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Comp, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__casl32|CASL|nicht signierte __int32 __casl32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Comp, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__casl64|CASL|nicht signierte __int64 __casl64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Comp, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__casal8|Casalb|nicht signierte __int8 __casal8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Comp, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__casal16|Casalh|nicht signierte __int16 __casal16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Comp, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__casal32|Casal|nicht signierte __int32 __casal32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Comp, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__casal64|Casal|nicht signierte __int64 __casal64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Comp, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__crc32b|CRC32B|nicht signierte __int32 __crc32b (unsignierte __int32, nicht signiertes __int32)|
|__crc32h|CRC32H|nicht signierte __int32 __crc32h (unsignierte __int32, nicht signiertes __int32)|
|__crc32w|CRC32W|nicht signierte __int32 __crc32w (unsignierte __int32, nicht signiertes __int32)|
|__crc32d|CRC32X|nicht signierte __int32 __crc32d (unsignierte __int32, nicht signiertes __int64)|
|__crc32cb|CRC32CB|nicht signierte __int32 __crc32cb (unsignierte __int32, nicht signiertes __int32)|
|__crc32ch|CRC32CH|nicht signierte __int32 __crc32ch (unsignierte __int32, nicht signiertes __int32)|
|__crc32cw|CRC32CW|nicht signierte __int32 __crc32cw (unsignierte __int32, nicht signiertes __int32)|
|__crc32cd|CRC32CX|nicht signierte __int32 __crc32cd (unsignierte __int32, nicht signiertes __int64)|
|__dmb|DMB|void __dmb(unsigned int `_Type`)<br /><br /> Fügt einen Speicherabgrenzungsvorgang in den Anweisungsstream ein. Der Parameter `_Type` gibt die Art der Einschränkung an, die die Grenze erzwingt.<br /><br /> Weitere Informationen zu den Arten von Einschränkungen, die erzwungen werden können, finden Sie unter Einschränkungen der Arbeits [Speicherbarriere](#BarrierRestrictions).|
|__dsb|DSB|void __dsb(unsigned int _Type)<br /><br /> Fügt einen Speicherabgrenzungsvorgang in den Anweisungsstream ein. Der Parameter `_Type` gibt die Art der Einschränkung an, die die Grenze erzwingt.<br /><br /> Weitere Informationen zu den Arten von Einschränkungen, die erzwungen werden können, finden Sie unter Einschränkungen der Arbeits [Speicherbarriere](#BarrierRestrictions).|
|__isb|ISB|void __isb(unsigned int _Type)<br /><br /> Fügt einen Speicherabgrenzungsvorgang in den Anweisungsstream ein. Der Parameter `_Type` gibt die Art der Einschränkung an, die die Grenze erzwingt.<br /><br /> Weitere Informationen zu den Arten von Einschränkungen, die erzwungen werden können, finden Sie unter Einschränkungen der Arbeits [Speicherbarriere](#BarrierRestrictions).|
|__getReg||nicht signierte __int64 __getReg (int)|
|__getRegFp||Double __getRegFp (int)|
|__getCallerReg||nicht signierte __int64 __getCallerReg (int)|
|__getCallerRegFp||Double __getCallerRegFp (int)|
|__hvc|HVC|unsigned int __hvc(unsigned int, ...)|
|__hlt|Zuerst|int __hlt (unsigniertes int,...)|
|__incx18byte||void-__incx18byte (unsigned long)|
|__incx18word||void-__incx18word (unsigned long)|
|__incx18dword||void-__incx18dword (unsigned long)|
|__incx18qword||void-__incx18qword (unsigned long)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (konstant volatile \__int16 \*)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (konstant volatile \__int32 \*)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (konstant volatile \__int64 \*)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (konstant volatile \__int8 \*)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_store16||void-__iso_volatile_store16 (volatile \__int16 \*, \__int16)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_store32||void-__iso_volatile_store32 (volatile \__int32 \*, \__int32)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_store64||void-__iso_volatile_store64 (volatile \__int64 \*, \__int64)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__iso_volatile_store8||void-__iso_volatile_store8 (volatile \__int8 \*, \__int8)<br /><br /> Weitere Informationen finden Sie unter [__iso_volatile_load/Store systeminternen Funktionen](#IsoVolatileLoadStore).|
|__ldar8|Ldarb|nicht signierte __int8 __ldar8 (unsignierte __int8 volatile * _Target)|
|__ldar16|Ldarh|nicht signierte __int16 __ldar16 (unsignierte __int16 volatile * _Target)|
|__ldar32|Ldar|nicht signierte __int32 __ldar32 (unsignierte __int32 volatile * _Target)|
|__ldar64|Ldar|nicht signierte __int64 __ldar64 (unsignierte __int64 volatile * _Target)|
|__ldapr8|Ldaprb|nicht signierte __int8 __ldapr8 (unsignierte __int8 volatile * _Target)|
|__ldapr16|Ldaprh|nicht signierte __int16 __ldapr16 (unsignierte __int16 volatile * _Target)|
|__ldapr32|Ldapr|nicht signierte __int32 __ldapr32 (unsignierte __int32 volatile * _Target)|
|__ldapr64|Ldapr|nicht signierte __int64 __ldapr64 (unsignierte __int64 volatile * _Target)|
|__mulh||\__int64 __mulh (\__int64, \__int64)|
|__prefetch|Prfm|void __cdecl \__prefetch (Konstante void \*)<br /><br /> Stellt einen `PRFM` Speicher Hinweis bereit, bei dem der Vorabruf Vorgang für das System `PLDL1KEEP` wird, auf den der Zugriff auf den Speicher oder die Nähe der angegebenen Adresse in Kürze möglicherweise Einige Systeme führen möglicherweise eine Optimierung für dieses Speicherzugriffsmuster aus, um die Leistung zur Laufzeit zu verbessern. Aus Sicht der C++-Sprache hat die Funktion jedoch keine sichtbaren Auswirkungen und hat möglicherweise gar keinen Nutzen.|
|__prefetch2|Prfm|void __cdecl \__prefetch (Konstante void \*, uint8_t PRF)<br /><br /> Stellt einen `PRFM` Memory-Hinweis mit dem bereitgestellten Vorabruf Vorgang für das System bereit, auf den möglicherweise in Kürze auf den Arbeitsspeicher oder die angegebene Adresse zugegriffen wird. Einige Systeme führen möglicherweise eine Optimierung für dieses Speicherzugriffsmuster aus, um die Leistung zur Laufzeit zu verbessern. Aus Sicht der C++-Sprache hat die Funktion jedoch keine sichtbaren Auswirkungen und hat möglicherweise gar keinen Nutzen.|
|__readx18byte||Ganzzahl ohne Vorzeichen char __readx18byte (Ganzzahl ohne Vorzeichen long)|
|__readx18word||kurz__readx18word ohne Vorzeichen (Ganzzahl ohne Vorzeichen long)|
|__readx18dword||Ganzzahl ohne Vorzeichen long-__readx18dword (Ganzzahl ohne Vorzeichen long)|
|__readx18qword||nicht signierte __int64 __readx18qword (Ganzzahl ohne Vorzeichen long)|
|__setReg||void-__setReg (int, Ganzzahl ohne Vorzeichen __int64)|
|__setRegFp||void-__setRegFp (int, Double)|
|__setCallerReg||void-__setCallerReg (int, Ganzzahl ohne Vorzeichen __int64)|
|__setCallerRegFp||void-__setCallerRegFp (int, Double)|
|__sev|SEV|void __sev(void)|
|__static_assert||void __static_assert (int, Konstante char \*)|
|__stlr8|Stlrb|void __stlr8 (unsignierte __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__stlr16|Stlrh|void __stlr16 (unsignierte __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__stlr32|Stlr|void __stlr32 (unsignierte __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__stlr64|Stlr|void __stlr64 (unsignierte __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__swp8|Austauschen|nicht signierte __int8 __swp8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__swp16|Austauschen|nicht signierte __int16 __swp16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__swp32|SWP|nicht signierte __int32 __swp32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__swp64|SWP|nicht signierte __int64 __swp64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__swpa8|Austausch Vorgänge|nicht signierte __int8 __swpa8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__swpa16|Austausch Vorgänge|nicht signierte __int16 __swpa16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__swpa32|Austauschen|nicht signierte __int32 __swpa32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__swpa64|Austauschen|nicht signierte __int64 __swpa64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__swpl8|Austausch Vorgänge|nicht signierte __int8 __swpl8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__swpl16|Austauschen|nicht signierte __int16 __swpl16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__swpl32|Austauschen|nicht signierte __int32 __swpl32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__swpl64|Austauschen|nicht signierte __int64 __swpl64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__swpal8|Austauschen|nicht signierte __int8 __swpal8 (Ganzzahl ohne Vorzeichen __int8 volatile * _Target, Ganzzahl ohne Vorzeichen __int8 _Value)|
|__swpal16|Austauschen|nicht signierte __int16 __swpal16 (Ganzzahl ohne Vorzeichen __int16 volatile * _Target, Ganzzahl ohne Vorzeichen __int16 _Value)|
|__swpal32|Austauschen|nicht signierte __int32 __swpal32 (Ganzzahl ohne Vorzeichen __int32 volatile * _Target, Ganzzahl ohne Vorzeichen __int32 _Value)|
|__swpal64|Austauschen|nicht signierte __int64 __swpal64 (Ganzzahl ohne Vorzeichen __int64 volatile * _Target, Ganzzahl ohne Vorzeichen __int64 _Value)|
|__sys|Einsetzt|Ganzzahl ohne Vorzeichen int __Sys (int, __int64)|
|__svc|SVC|Ganzzahl ohne Vorzeichen int-__svc (Ganzzahl ohne Vorzeichen int,...)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|__writex18byte||void-__writex18byte (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen Char)|
|__writex18word||void-__writex18word (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen Short)|
|__writex18dword||void-__writex18dword (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen long)|
|__writex18qword||void-__writex18qword (Ganzzahl ohne Vorzeichen long, Ganzzahl ohne Vorzeichen __int64)|
|__umulh||nicht signierte \__int64 __umulh (unsignierte \__int64, ohne Vorzeichen \__int64)|
|_CopyDoubleFromInt64||doppelte _CopyDoubleFromInt64 (\__int64)|
|_CopyFloatFromInt32||float-_CopyFloatFromInt32 (\__int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(double)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(unsigned long)|
|_CountLeadingOnes64||Ganzzahl ohne Vorzeichen int _CountLeadingOnes64 (Ganzzahl ohne Vorzeichen \__int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||Ganzzahl ohne Vorzeichen int _CountLeadingSigns64 (\__int64)|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(unsigned long)|
|_CountLeadingZeros64||Ganzzahl ohne Vorzeichen int _CountLeadingZeros64 (Ganzzahl ohne Vorzeichen \__int64)|
|_ReadStatusReg|MRS|\__int64 _ReadStatusReg (int)|
|_WriteStatusReg|MSR|void _WriteStatusReg (int, \__int64)|

[[An den Anfang zurückkehren](#top)]

###  <a name="BarrierRestrictions"></a>Einschränkungen der Arbeitsspeicher Barriere

Die intrinsischen Funktionen `__dmb` (Datenspeicher Barriere), `__dsb` (Daten Synchronisierungs Barriere) und `__isb` (Anweisungs Synchronisierungs Barriere) verwenden die folgenden vordefinierten Werte, um die Einschränkung der Arbeitsspeicher Barriere in Bezug auf die Freigabe Domäne und die Art des Zugriffs anzugeben, die vom Vorgang betroffen sind.

|Einschränkungswert|Beschreibung|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|Gesamtes System, Lese- und Schreibvorgänge.|
|_ARM64_BARRIER_ST|Gesamtes System, nur Schreibvorgänge.|
|_ARM64_BARRIER_LD|Vollständiges System, schreibgeschützt.|
|_ARM64_BARRIER_ISH|Innen teilbar, Lese- und Schreibvorgänge.|
|_ARM64_BARRIER_ISHST|Innen teilbar, nur Schreibvorgänge.|
|_ARM64_BARRIER_ISHLD|Innerer Sharable, schreibgeschützt.|
|_ARM64_BARRIER_NSH|Nicht teilbar, Lese- und Schreibvorgänge.|
|_ARM64_BARRIER_NSHST|Nicht teilbar, nur Schreibvorgänge.|
|_ARM64_BARRIER_NSHLD|Nicht Sharable, schreibgeschützt.|
|_ARM64_BARRIER_OSH|Außen teilbar, Lese- und Schreibvorgänge.|
|_ARM64_BARRIER_OSHST|Außen teilbar, nur Schreibvorgänge.|
|_ARM64_BARRIER_OSHLD|Äußerer Sharable, schreibgeschützt.|

Bei der `__isb` systeminternen Einschränkung ist die einzige derzeit gültige Einschränkung _ARM64_BARRIER_SY. alle anderen Werte sind von der Architektur reserviert.

###  <a name="IsoVolatileLoadStore"></a>systeminterne __iso_volatile_load/Store

Diese intrinsischen Funktionen führen explizit Lade-und Speichervorgänge aus, die nicht Compileroptimierungen unterliegen.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>Parameter

*Speicherort*\
Die Adresse eines Speicherbereichs für Lese- oder Schreibvorgänge.

*Wert*\
Der Wert, der in den angegebenen Speicherort geschrieben werden soll (nur systeminterne Speicherorte).

#### <a name="return-value-load-intrinsics-only"></a>Rückgabewert (nur systeminterne Funktionen laden)

Der Wert des Speicher Orts, der durch den *Speicherort*angegeben wird.

#### <a name="remarks"></a>Hinweise

Sie können die systeminternen Funktionen `__iso_volatile_load8/16/32/64` und `__iso_volatile_store8/16/32/64` verwenden, um explizit Speicherzugriffe auszuführen, die nicht Compileroptimierungen unterliegen. Der Compiler kann die relative Reihenfolge dieser Vorgänge nicht entfernen, synthetisieren oder ändern. Es werden jedoch keine impliziten Hardware Speicherbarrieren generiert. Aus diesem Grund kann die Hardware die sichtbaren Speicherzugriffe möglicherweise immer noch über mehrere Threads hinweg neu anordnen. Genauer gilt, entsprechen diese systeminternen Funktionen den folgenden Ausdrücken, die unter **/volatile: ISO**kompiliert werden.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

Beachten Sie, dass die systeminternen Funktionen flüchtige Zeiger verwenden, um flüchtige Variablen zu berücksichtigen. Es ist jedoch keine Anforderung oder Empfehlung, flüchtige Zeiger als Argumente zu verwenden. Die Semantik dieser Vorgänge ist genau dasselbe, wenn ein regulärer, nicht flüchtiger Typ verwendet wird.

Weitere Informationen zum Befehlszeilenargument **/volatile: ISO** finden Sie unter [/volatile (volatile-Schlüsselwort Interpretation)](../build/reference/volatile-volatile-keyword-interpretation.md).

##  <a name="I"></a>ARM64-Unterstützung für systeminterne Funktionen aus anderen Architekturen

In der folgenden Tabelle werden die systeminternen Funktionen aus anderen Architekturen aufgelistet, die auf ARM64-Plattformen unterstützt werden Wenn das Verhalten einer systeminternen Funktion auf ARM64 vom Verhalten anderer Hardwarearchitekturen abweicht, werden weitere Details vermerkt.

|Funktionsname|Funktionsprototyp|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|void-__code_seg (Konstante char \*)|
|__debugbreak|void __cdecl \__debugbreak (void)|
|__fastfail|__declspec (noreturn) void \__fastfail (unsigned int)|
|__nop|void __nop(void)|
|__yield|void __yield (void) **Hinweis:** auf ARM64-Plattformen generiert diese Funktion die yield-Anweisung. Diese Anweisung gibt an, dass der Thread eine Aufgabe ausführt, die möglicherweise vorübergehend von der Ausführung angehalten wird, z. –. ein Spinlock – ohne Beeinträchtigung des Programms. Sie ermöglicht der CPU, andere Tasks während Ausführungs Zyklen auszuführen, die andernfalls verschwendet würden.|
|_AddressOfReturnAddress|void \* _AddressOfReturnAddress (void)|
|_BitScanForward|Ganzzahl ohne Vorzeichen char _BitScanForward (Ganzzahl ohne Vorzeichen long \* _index, Ganzzahl ohne Vorzeichen long _Mask)|
|_BitScanForward64|Ganzzahl ohne Vorzeichen char _BitScanForward64 (Ganzzahl ohne Vorzeichen long \* _index, Ganzzahl ohne Vorzeichen __int64 _Mask)|
|_BitScanReverse|Ganzzahl ohne Vorzeichen char _BitScanReverse (Ganzzahl ohne Vorzeichen long \* _index, Ganzzahl ohne Vorzeichen long _Mask)|
|_BitScanReverse64|Ganzzahl ohne Vorzeichen char _BitScanReverse64 (Ganzzahl ohne Vorzeichen long \* _index, Ganzzahl ohne Vorzeichen __int64 _Mask)|
|_bittest|Ganzzahl ohne Vorzeichen char _bittest (Long Konstanten \*, Long)|
|_bittest64|Ganzzahl ohne Vorzeichen char _bittest64 (__int64 Konstanten \*, __int64)|
|_bittestandcomplement|Ganzzahl ohne Vorzeichen char _bittestandcomplement (Long \*, Long)|
|_bittestandcomplement64|Ganzzahl ohne Vorzeichen char _bittestandcomplement64 (__int64 \*, __int64)|
|_bittestandreset|Ganzzahl ohne Vorzeichen char _bittestandreset (Long \*, Long)|
|_bittestandreset64|Ganzzahl ohne Vorzeichen char _bittestandreset64 (__int64 \*, __int64)|
|_bittestandset|Ganzzahl ohne Vorzeichen char _bittestandset (Long \*, Long)|
|_bittestandset64|Ganzzahl ohne Vorzeichen char _bittestandset64 (__int64 \*, __int64)|
|_byteswap_uint64|nicht signierte __int64 \__cdecl _byteswap_uint64 (Ganzzahl ohne Vorzeichen \__int64)|
|_byteswap_ulong|unsigned long __cdecl _byteswap_ulong(unsigned long)|
|_byteswap_ushort|unsigned short __cdecl _byteswap_ushort(unsigned short)|
|_disable|void __cdecl _disable (void) **Hinweis:** auf ARM64-Plattformen generiert diese Funktion die Anweisung `MSR DAIFCLR,#2`; Es ist nur als systeminterne Funktion verfügbar.|
|_enable|void __cdecl _enable (void) **Hinweis:** auf ARM64-Plattformen generiert diese Funktion die Anweisung `MSR DAIFSET,#2`; Es ist nur als systeminterne Funktion verfügbar.|
|_lrotl|unsigned long __cdecl _lrotl(unsigned long, int)|
|_lrotr|unsigned long __cdecl _lrotr(unsigned long, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|void \* _ReturnAddress (void)|
|_rotl|unsigned int __cdecl _rotl(unsigned int _Value, int _Shift)|
|_rotl16|unsigned short _rotl16(unsigned short _Value, unsigned char _Shift)|
|_rotl64|nicht signierte __int64 \__cdecl _rotl64 (Ganzzahl ohne Vorzeichen \__int64 _Value, int _Shift)|
|_rotl8|unsigned char _rotl8(unsigned char _Value, unsigned char _Shift)|
|_rotr|unsigned int __cdecl _rotr(unsigned int _Value, int _Shift)|
|_rotr16|unsigned short _rotr16(unsigned short _Value, unsigned char _Shift)|
|_rotr64|nicht signierte __int64 \__cdecl _rotr64 (Ganzzahl ohne Vorzeichen \__int64 _Value, int _Shift)|
|_rotr8|unsigned char _rotr8(unsigned char _Value, unsigned char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[An den Anfang zurückkehren](#top)]

## <a name="interlocked-intrinsics"></a>Intrinsie intrinsie systeminterne Funktionen

Ineinandergreifende systeminterne Funktionen sind eine Reihe von systeminternen Funktionen, die zum Ausführen atomarer Lese-Änderungs-Schreib-Vorgänge verwendet werden. Einige davon sind auf allen Plattformen verfügbar. Sie sind hier separat aufgeführt, da es eine große Anzahl von Ihnen gibt. Da ihre Definitionen größtenteils redundant sind, ist es einfacher, Sie in allgemeinen Begriffen zu betrachten. Die genauen Verhaltensweisen können von den Namen abgeleitet werden.

In der folgenden Tabelle wird die ARM64-Unterstützung der systeminternen nicht-bittest-Funktionen zusammengefasst. Jede Zelle in der Tabelle entspricht einem Namen, der durch Anhängen des Vorgangsnamens in der am weitesten links befindlichen Zelle der Zeile und des Typnamens in der obersten Zelle der Spalte an `_Interlocked` abgeleitet wird. Beispielsweise entspricht die Zelle an der Schnittmenge der `Xor` Zeile und der Spalte `8` `_InterlockedXor8` und wird vollständig unterstützt. Die meisten unterstützten Funktionen bieten diese optionalen Suffixe: `_acq`, `_rel` und `_nf`. Das `_acq`-Suffix gibt eine „Acquire“-Semantik zum Abrufen an, und das `_rel`-Suffix gibt eine „Release“-Semantik zum Freigeben an. Der `_nf`-oder "No fence"-Suffix ist für Arm und ARM64 eindeutig und wird im nächsten Abschnitt erläutert.

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|Hinzufügen|Keiner|Keiner|Vollständig|Vollständig|Keiner|Keiner|
|And|Vollständig|Vollständig|Vollständig|Vollständig|Keiner|Keiner|
|CompareExchange|Vollständig|Vollständig|Vollständig|Vollständig|Vollständig|Vollständig|
|Dekrement|Keiner|Vollständig|Vollständig|Vollständig|Keiner|Keiner|
|Exchange|Vollständig|Vollständig|Vollständig|Vollständig|Keiner|Vollständig|
|ExchangeAdd|Vollständig|Vollständig|Vollständig|Vollständig|Keiner|Keiner|
|Inkrement|Keiner|Vollständig|Vollständig|Vollständig|Keiner|Keiner|
|Or|Vollständig|Vollständig|Vollständig|Vollständig|Keiner|Keiner|
|Xor|Vollständig|Vollständig|Vollständig|Vollständig|Keiner|Keiner|

Key:

- **Full**: unterstützt die Formulare Plain, `_acq`, `_rel`und `_nf`.

- **Keine**: nicht unterstützt

###  <a name="nf_suffix"></a>_nf Suffix (kein Fence)

Das Suffix "`_nf`" oder "No fence" gibt an, dass sich der Vorgang nicht als irgendeine Art von Speicherbarriere verhält, im Gegensatz zu den anderen drei Formen (Plain, `_acq`und `_rel`), die alle sich als eine Art Barriere Verhalten. Eine mögliche Verwendung der `_nf` Formularen besteht darin, einen Statistik Leistungswert beizubehalten, der gleichzeitig von mehreren Threads aktualisiert wird, dessen Wert jedoch nicht anderweitig verwendet wird, während mehrere Threads ausgeführt werden.

### <a name="list-of-interlocked-intrinsics"></a>Liste der intrinsie systeminternen Funktionen

|Funktionsname|Funktionsprototyp|
|-------------------|------------------------|
|_InterlockedAdd|Long-_InterlockedAdd (Long _volatile \*, Long)|
|_InterlockedAdd64|__int64 _InterlockedAdd64 (\__int64 volatile \*, \__int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq (\__int64 volatile \*, \__int64)|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf (\__int64 volatile \*, \__int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel (\__int64 volatile \*, \__int64)|
|_InterlockedAdd_acq|Long-_InterlockedAdd_acq (langes flüchtiges \*, Long)|
|_InterlockedAdd_nf|Long-_InterlockedAdd_nf (langes flüchtiges \*, Long)|
|_InterlockedAdd_rel|Long-_InterlockedAdd_rel (langes flüchtiges \*, Long)|
|_InterlockedAnd|Long-_InterlockedAnd (langes flüchtiges \*, Long)|
|_InterlockedAnd16|kurz_InterlockedAnd16 (kurzes flüchtiges \*, kurz)|
|_InterlockedAnd16_acq|kurz_InterlockedAnd16_acq (kurzes flüchtiges \*, kurz)|
|_InterlockedAnd16_nf|kurz_InterlockedAnd16_nf (kurzes flüchtiges \*, kurz)|
|_InterlockedAnd16_rel|kurz_InterlockedAnd16_rel (kurzes flüchtiges \*, kurz)|
|_InterlockedAnd64|__int64 _InterlockedAnd64 (\__int64 volatile \*, \__int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq (\__int64 volatile \*, \__int64)|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf (\__int64 volatile \*, \__int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel (\__int64 volatile \*, \__int64)|
|_InterlockedAnd8|char-_InterlockedAnd8 (Char volatile \*, Char)|
|_InterlockedAnd8_acq|char-_InterlockedAnd8_acq (Char volatile \*, Char)|
|_InterlockedAnd8_nf|char-_InterlockedAnd8_nf (Char volatile \*, Char)|
|_InterlockedAnd8_rel|char-_InterlockedAnd8_rel (Char volatile \*, Char)|
|_InterlockedAnd_acq|Long-_InterlockedAnd_acq (langes flüchtiges \*, Long)|
|_InterlockedAnd_nf|Long-_InterlockedAnd_nf (langes flüchtiges \*, Long)|
|_InterlockedAnd_rel|Long-_InterlockedAnd_rel (langes flüchtiges \*, Long)|
|_InterlockedCompareExchange|Long-__cdecl _InterlockedCompareExchange (langes flüchtiges \*, Long, Long)|
|_InterlockedCompareExchange_acq|Long-_InterlockedCompareExchange_acq (Long volatile \*, Long, Long)|
|_InterlockedCompareExchange_nf|Long-_InterlockedCompareExchange_nf (Long volatile \*, Long, Long)|
|_InterlockedCompareExchange_rel|Long-_InterlockedCompareExchange_rel (Long volatile \*, Long, Long)|
|_InterlockedCompareExchange16|kurz_InterlockedCompareExchange16 (kurzes flüchtiges \*, kurz, kurz)|
|_InterlockedCompareExchange16_acq|kurz_InterlockedCompareExchange16_acq (kurzes flüchtiges \*, kurz, kurz)|
|_InterlockedCompareExchange16_nf|kurz_InterlockedCompareExchange16_nf (kurzes flüchtiges \*, kurz, kurz)|
|_InterlockedCompareExchange16_rel|kurz_InterlockedCompareExchange16_rel (kurzes flüchtiges \*, kurz, kurz)|
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64 (\__int64 volatile \*\__int64, \__int64)|
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq (\__int64 volatile \*\__int64, \__int64)|
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf (\__int64 volatile \*\__int64, \__int64)|
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel (\__int64 volatile \*\__int64, \__int64)|
|_InterlockedCompareExchange8|char-_InterlockedCompareExchange8 (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_acq|char-_InterlockedCompareExchange8_acq (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_nf|char-_InterlockedCompareExchange8_nf (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_rel|char-_InterlockedCompareExchange8_rel (Char volatile \*, Char, Char)|
|_InterlockedCompareExchangePointer|void \* _InterlockedCompareExchangePointer (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_acq|void \* _InterlockedCompareExchangePointer_acq (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_nf|void \* _InterlockedCompareExchangePointer_nf (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_rel|void \* _InterlockedCompareExchangePointer_rel (void \* volatile \*, void \*, void \*)|
|_InterlockedCompareExchange128|nicht signiertes char-_InterlockedCompareExchange128 (\__int64 volatile \* _Destination \__int64 _ExchangeHigh \_, _int64 _ExchangeLow \_, _int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_acq|nicht signiertes char-_InterlockedCompareExchange128_acq (\__int64 volatile \* _Destination \__int64 _ExchangeHigh \_, _int64 _ExchangeLow \_, _int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_nf|nicht signiertes char-_InterlockedCompareExchange128_nf (\__int64 volatile \* _Destination \__int64 _ExchangeHigh \_, _int64 _ExchangeLow \_, _int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_rel|nicht signiertes char-_InterlockedCompareExchange128_rel (\__int64 volatile \* _Destination \__int64 _ExchangeHigh \_, _int64 _ExchangeLow \_, _int64 \* _ComparandResult)|
|_InterlockedDecrement|lange __cdecl _InterlockedDecrement (langes flüchtiges \*)|
|_InterlockedDecrement16|kurz_InterlockedDecrement16 (kurzes flüchtiges \*)|
|_InterlockedDecrement16_acq|kurz_InterlockedDecrement16_acq (kurzes flüchtiges \*)|
|_InterlockedDecrement16_nf|kurz_InterlockedDecrement16_nf (kurzes flüchtiges \*)|
|_InterlockedDecrement16_rel|kurz_InterlockedDecrement16_rel (kurzes flüchtiges \*)|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64 (\__int64 volatile \*)|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq (\__int64 volatile \*)|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf (\__int64 volatile \*)|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel (\__int64 volatile \*)|
|_InterlockedDecrement_acq|Long-_InterlockedDecrement_acq (langes flüchtiges \*)|
|_InterlockedDecrement_nf|Long-_InterlockedDecrement_nf (langes flüchtiges \*)|
|_InterlockedDecrement_rel|Long-_InterlockedDecrement_rel (langes flüchtiges \*)|
|_InterlockedExchange|lange __cdecl _InterlockedExchange (langes flüchtiges \* _Target, Long)|
|_InterlockedExchange_acq|Long-_InterlockedExchange_acq (langes flüchtiges \* _Target, Long)|
|_InterlockedExchange_nf|Long-_InterlockedExchange_nf (langes flüchtiges \* _Target, Long)|
|_InterlockedExchange_rel|Long-_InterlockedExchange_rel (langes flüchtiges \* _Target, Long)|
|_InterlockedExchange16|kurz_InterlockedExchange16 (kurzes flüchtiges \* _Target, kurz)|
|_InterlockedExchange16_acq|kurz_InterlockedExchange16_acq (kurzes flüchtiges \* _Target, kurz)|
|_InterlockedExchange16_nf|kurz_InterlockedExchange16_nf (kurzes flüchtiges \* _Target, kurz)|
|_InterlockedExchange16_rel|kurz_InterlockedExchange16_rel (kurzes flüchtiges \* _Target, kurz)|
|_InterlockedExchange64|__int64 _InterlockedExchange64 (\__int64 volatile \* _Target \__int64)|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq (\__int64 volatile \* _Target \__int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf (\__int64 volatile \* _Target \__int64)|
|_InterlockedExchange64_rel|__int64 _InterlockedExchange64_rel (\__int64 volatile \* _Target \__int64)|
|_InterlockedExchange8|char-_InterlockedExchange8 (Char volatile \* _Target, Char)|
|_InterlockedExchange8_acq|char-_InterlockedExchange8_acq (Char volatile \* _Target, Char)|
|_InterlockedExchange8_nf|char-_InterlockedExchange8_nf (Char volatile \* _Target, Char)|
|_InterlockedExchange8_rel|char-_InterlockedExchange8_rel (Char volatile \* _Target, Char)|
|_InterlockedExchangeAdd|Long-__cdecl _InterlockedExchangeAdd (langes flüchtiges \*, Long)|
|_InterlockedExchangeAdd16|kurz_InterlockedExchangeAdd16 (kurzes flüchtiges \*, kurz)|
|_InterlockedExchangeAdd16_acq|kurz_InterlockedExchangeAdd16_acq (kurzes flüchtiges \*, kurz)|
|_InterlockedExchangeAdd16_nf|kurz_InterlockedExchangeAdd16_nf (kurzes flüchtiges \*, kurz)|
|_InterlockedExchangeAdd16_rel|kurz_InterlockedExchangeAdd16_rel (kurzes flüchtiges \*, kurz)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64 (\__int64 volatile \*, \__int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq (\__int64 volatile \*, \__int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf (\__int64 volatile \*, \__int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel (\__int64 volatile \*, \__int64)|
|_InterlockedExchangeAdd8|char-_InterlockedExchangeAdd8 (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_acq|char-_InterlockedExchangeAdd8_acq (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_nf|char-_InterlockedExchangeAdd8_nf (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_rel|char-_InterlockedExchangeAdd8_rel (Char volatile \*, Char)|
|_InterlockedExchangeAdd_acq|Long-_InterlockedExchangeAdd_acq (langes flüchtiges \*, Long)|
|_InterlockedExchangeAdd_nf|Long-_InterlockedExchangeAdd_nf (langes flüchtiges \*, Long)|
|_InterlockedExchangeAdd_rel|Long-_InterlockedExchangeAdd_rel (langes flüchtiges \*, Long)|
|_InterlockedExchangePointer|void \* _InterlockedExchangePointer (void \* volatile \* _Target, void \*)|
|_InterlockedExchangePointer_acq|void \* _InterlockedExchangePointer_acq (void \* volatile \* _Target, void \*)|
|_InterlockedExchangePointer_nf|void \* _InterlockedExchangePointer_nf (void \* volatile \* _Target, void \*)|
|_InterlockedExchangePointer_rel|void \* _InterlockedExchangePointer_rel (void \* volatile \* _Target, void \*)|
|_InterlockedIncrement|lange __cdecl _InterlockedIncrement (langes flüchtiges \*)|
|_InterlockedIncrement16|kurz_InterlockedIncrement16 (kurzes flüchtiges \*)|
|_InterlockedIncrement16_acq|kurz_InterlockedIncrement16_acq (kurzes flüchtiges \*)|
|_InterlockedIncrement16_nf|kurz_InterlockedIncrement16_nf (kurzes flüchtiges \*)|
|_InterlockedIncrement16_rel|kurz_InterlockedIncrement16_rel (kurzes flüchtiges \*)|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64 (\__int64 volatile \*)|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq (\__int64 volatile \*)|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf (\__int64 volatile \*)|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel (\__int64 volatile \*)|
|_InterlockedIncrement_acq|Long-_InterlockedIncrement_acq (langes flüchtiges \*)|
|_InterlockedIncrement_nf|Long-_InterlockedIncrement_nf (langes flüchtiges \*)|
|_InterlockedIncrement_rel|Long-_InterlockedIncrement_rel (langes flüchtiges \*)|
|_InterlockedOr|Long-_InterlockedOr (langes flüchtiges \*, Long)|
|_InterlockedOr16|kurz_InterlockedOr16 (kurzes flüchtiges \*, kurz)|
|_InterlockedOr16_acq|kurz_InterlockedOr16_acq (kurzes flüchtiges \*, kurz)|
|_InterlockedOr16_nf|kurz_InterlockedOr16_nf (kurzes flüchtiges \*, kurz)|
|_InterlockedOr16_rel|kurz_InterlockedOr16_rel (kurzes flüchtiges \*, kurz)|
|_InterlockedOr64|__int64 _InterlockedOr64 (\__int64 volatile \*, \__int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq (\__int64 volatile \*, \__int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf (\__int64 volatile \*, \__int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel (\__int64 volatile \*, \__int64)|
|_InterlockedOr8|char-_InterlockedOr8 (Char volatile \*, Char)|
|_InterlockedOr8_acq|char-_InterlockedOr8_acq (Char volatile \*, Char)|
|_InterlockedOr8_nf|char-_InterlockedOr8_nf (Char volatile \*, Char)|
|_InterlockedOr8_rel|char-_InterlockedOr8_rel (Char volatile \*, Char)|
|_InterlockedOr_acq|Long-_InterlockedOr_acq (langes flüchtiges \*, Long)|
|_InterlockedOr_nf|Long-_InterlockedOr_nf (langes flüchtiges \*, Long)|
|_InterlockedOr_rel|Long-_InterlockedOr_rel (langes flüchtiges \*, Long)|
|_InterlockedXor|Long-_InterlockedXor (langes flüchtiges \*, Long)|
|_InterlockedXor16|kurz_InterlockedXor16 (kurzes flüchtiges \*, kurz)|
|_InterlockedXor16_acq|kurz_InterlockedXor16_acq (kurzes flüchtiges \*, kurz)|
|_InterlockedXor16_nf|kurz_InterlockedXor16_nf (kurzes flüchtiges \*, kurz)|
|_InterlockedXor16_rel|kurz_InterlockedXor16_rel (kurzes flüchtiges \*, kurz)|
|_InterlockedXor64|__int64 _InterlockedXor64 (\__int64 volatile \*, \__int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq (\__int64 volatile \*, \__int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf (\__int64 volatile \*, \__int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel (\__int64 volatile \*, \__int64)|
|_InterlockedXor8|char-_InterlockedXor8 (Char volatile \*, Char)|
|_InterlockedXor8_acq|char-_InterlockedXor8_acq (Char volatile \*, Char)|
|_InterlockedXor8_nf|char-_InterlockedXor8_nf (Char volatile \*, Char)|
|_InterlockedXor8_rel|char-_InterlockedXor8_rel (Char volatile \*, Char)|
|_InterlockedXor_acq|Long-_InterlockedXor_acq (langes flüchtiges \*, Long)|
|_InterlockedXor_nf|Long-_InterlockedXor_nf (langes flüchtiges \*, Long)|
|_InterlockedXor_rel|Long-_InterlockedXor_rel (langes flüchtiges \*, Long)|

[[An den Anfang zurückkehren](#top)]

### <a name="_interlockedbittest-intrinsics"></a>intrinsie _interlockedbittest

Die einfachen Interlocked-bittests sind für alle Plattformen üblich. ARM64 fügt `_acq`-, `_rel`-und `_nf` Varianten hinzu, die nur die Sperrungs Semantik eines Vorgangs ändern, wie in [_nf (No Fence)-Suffix](#nf_suffix) weiter oben in diesem Artikel beschrieben.

|Funktionsname|Funktionsprototyp|
|-------------------|------------------------|
|_interlockedbittestandreset|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset (Long volatile \*, Long)|
|_interlockedbittestandreset_acq|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset_acq (Long volatile \*, Long)|
|_interlockedbittestandreset_nf|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset_nf (Long volatile \*, Long)|
|_interlockedbittestandreset_rel|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset_rel (Long volatile \*, Long)|
|_interlockedbittestandreset64|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset64 (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_acq|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset64_acq (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_nf|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset64_nf (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_rel|Ganzzahl ohne Vorzeichen char _interlockedbittestandreset64_rel (__int64 volatile \*, __int64)|
|_interlockedbittestandset|Ganzzahl ohne Vorzeichen char _interlockedbittestandset (Long volatile \*, Long)|
|_interlockedbittestandset_acq|Ganzzahl ohne Vorzeichen char _interlockedbittestandset_acq (Long volatile \*, Long)|
|_interlockedbittestandset_nf|Ganzzahl ohne Vorzeichen char _interlockedbittestandset_nf (Long volatile \*, Long)|
|_interlockedbittestandset_rel|Ganzzahl ohne Vorzeichen char _interlockedbittestandset_rel (Long volatile \*, Long)|
|_interlockedbittestandset64|Ganzzahl ohne Vorzeichen char _interlockedbittestandset64 (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_acq|Ganzzahl ohne Vorzeichen char _interlockedbittestandset64_acq (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_nf|Ganzzahl ohne Vorzeichen char _interlockedbittestandset64_nf (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_rel|Ganzzahl ohne Vorzeichen char _interlockedbittestandset64_rel (__int64 volatile \*, __int64)|

[[An den Anfang zurückkehren](#top)]

## <a name="see-also"></a>Siehe auch

Systeminterne [Compilerfunktionen](../intrinsics/compiler-intrinsics.md)\
Systeminterne [Arm](arm-intrinsics.md) -Funktionen\
[Arm-Assembler-Verweis](../assembler/arm/arm-assembler-reference.md)\
[C++Sprachreferenz](../cpp/cpp-language-reference.md)
