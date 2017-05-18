---
title: zugriffstastenklasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMPRT/accelerator
- AMPRT/Concurrency::accelerator::accelerator
- AMPRT/Concurrency::accelerator::create_view
- AMPRT/Concurrency::accelerator::get_all
- AMPRT/Concurrency::accelerator::get_auto_selection_view
- AMPRT/Concurrency::accelerator::get_dedicated_memory
- AMPRT/Concurrency::accelerator::get_default_cpu_access_type
- AMPRT/Concurrency::accelerator::get_default_view
- AMPRT/Concurrency::accelerator::get_description
- AMPRT/Concurrency::accelerator::get_device_path
- AMPRT/Concurrency::accelerator::get_has_display
- AMPRT/Concurrency::accelerator::get_is_debug
- AMPRT/Concurrency::accelerator::get_is_emulated
- AMPRT/Concurrency::accelerator::get_supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::get_supports_double_precision
- AMPRT/Concurrency::accelerator::get_supports_limited_double_precision
- AMPRT/Concurrency::accelerator::get_version
- AMPRT/Concurrency::accelerator::set_default
- AMPRT/Concurrency::accelerator::set_default_cpu_access_type
- AMPRT/Concurrency::accelerator::cpu_accelerator
- AMPRT/Concurrency::accelerator::dedicated_memory
- AMPRT/Concurrency::accelerator::default_accelerator
- AMPRT/Concurrency::accelerator::default_cpu_access_type
- AMPRT/Concurrency::accelerator::default_view
- AMPRT/Concurrency::accelerator::description
- AMPRT/Concurrency::accelerator::device_path
- AMPRT/Concurrency::accelerator::direct3d_ref
- AMPRT/Concurrency::accelerator::direct3d_warp
- AMPRT/Concurrency::accelerator::has_display
- AMPRT/Concurrency::accelerator::is_debug
- AMPRT/Concurrency::accelerator::is_emulated
- AMPRT/Concurrency::accelerator::supports_cpu_shared_memory
- AMPRT/Concurrency::accelerator::supports_double_precision
- AMPRT/Concurrency::accelerator::supports_limited_double_precision
- AMPRT/Concurrency::accelerator::version
dev_langs:
- C++
helpviewer_keywords:
- accelerator class
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d1e68b3533452ec1e47053086c59654337c995fa
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="accelerator-class"></a>Zugriffstastenklasse
Eine Zugriffstaste ist eine Hardwarefunktion, die für datenparallele Computervorgänge optimiert ist. Eine Zugriffstaste ist ein Gerät, das einem PCIe-Bus angefügt wird (wie einem GPU-Computer), oder es handelt sich um einen erweiterten Befehl, der auf der Haupt-CPU festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `accelerator`-Klasse.|  
|[~ Accelerator-Destruktor](#ctor)|Zerstört das `accelerator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CREATE_VIEW](#create_view)|Erstellt und gibt ein `accelerator_view`-Objekt auf dieser Zugriffstaste zurück.|  
|[get_all](#get_all)|Gibt einen Vektor von `accelerator`-Objekten zurück, die alle verfügbaren Zugriffstasten darstellen.|  
|[get_auto_selection_view](#get_auto_selection_view)|Gibt das `accelerator_view`-Objekt für die automatische Auswahl zurück.|  
|[get_dedicated_memory](#get_dedicated_memory)|Gibt den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB zurück.|  
|[get_default_cpu_access_type](#get_default_cpu_access_type)|Gibt den Standardwert zurück [Access_type](concurrency-namespace-enums-amp.md#access_type) für die Puffer auf dieser Zugriffstaste erstellt.|  
|[get_default_view](#get_default_view)|Gibt das standardmäßige `accelerator_view`-Objekt zurück, das mit dem `accelerator`-Objekt verknüpft ist.|  
|[get_Description](#get_description)|Gibt eine kurze Beschreibung des `accelerator`-Geräts zurück.|  
|[get_device_path](#get_device_path)|Gibt den Pfad des physischen Geräts zurück.|  
|[get_has_display](#get_has_display)|Bestimmt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[get_is_debug](#get_is_debug)|Bestimmt, für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[get_is_emulated](#get_is_emulated)|Bestimmt, ob das `accelerator`-Objekt emuliert ist.|  
|[get_supports_cpu_shared_memory](#get_supports_cpu_shared_memory)|Bestimmt, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt|  
|[get_supports_double_precision](#get_supports_double_precision)|Bestimmt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[get_supports_limited_double_precision](#get_supports_limited_double_precision)|Bestimmt, ob das `accelerator`-Objekt über beschränkte Unterstützung für mathematische Funktionen mit doppelter Genauigkeit verfügt.|  
|[get_version](#get_version)|Gibt die Version des `accelerator`-Objekts zurück.|  
|[set_default](#set_default)|Gibt den Pfad der Standardzugriffstaste zurück.|  
|[set_default_cpu_access_type](#set_default_cpu_access_type)|Legt die Standard-CPU [Access_type](concurrency-namespace-enums-amp.md#access_type)für Arrays und implizite speicherbelegungen für diese `accelerator`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[operator!=](#operator_neq)|Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.|  
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `accelerator`-Objekts in dieses Objekt.|  
|[operator==](#operator_eq_eq)|Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[cpu_accelerator](#cpu_accelerator)|Ruft eine Zeichenfolgenkonstante für die CPU-`accelerator` ab.|  
|[dedicated_memory](#dedicated_memory)|Ruft den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB ab.|  
|[default_accelerator](#default_accelerator)|Ruft eine Zeichenfolgenkonstante für die standardmäßige `accelerator` ab.|  
|[default_cpu_access_type-Objekt](#default_cpu_access_type)|Ruft ab oder legt die Standard-CPU [Access_type](concurrency-namespace-enums-amp.md#access_type)für Arrays und implizite speicherbelegungen für diese `accelerator`.|  
|[default_view](#default_view)|Ruft das standardmäßige `accelerator_view`-Objekt ab, das dem `accelerator`-Element zugeordnet ist.|  
|[Beschreibung](#description)|Ruft eine kurze Beschreibung des `accelerator`-Geräts ab.|  
|[device_path](#device_path)|Ruft den Pfad des physischen Geräts ab.|  
|[direct3d_ref](#direct3d_ref)|Ruft eine Zeichenfolgenkonstante für eine Direct3D-Verweis-`accelerator` ab.|  
|[direct3d_warp](#direct3d_warp)|Ruft die Zeichenfolge für die Konstante ein `accelerator` Objekt, das Sie verwenden können, für die Ausführung von C++ AMP-Codes auf Multikern-CPUs, die Streaming SIMD Extensions (SSE) verwenden.|  
|[has_display](#has_display)|Ruft einen booleschen Wert ab, der angibt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[is_debug](#is_debug)|Gibt an, ob für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[is_emulated](#is_emulated)|Gibt an, ob das `accelerator`-Objekt emuliert ist.|  
|[supports_cpu_shared_memory](#supports_cpu_shared_memory)|Gibt an, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt.|  
|[supports_double_precision](#supports_double_precision)|Gibt an, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt.|  
|[supports_limited_double_precision](#supports_limited_double_precision)|Gibt an, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen mit doppelter Genauigkeit verfügt.|  
|[version](#version)|Ruft die Version der `accelerator` ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `accelerator`  
  
## <a name="remarks"></a>Hinweise  
 Eine Zugriffstaste ist eine Hardwarefunktion, die für datenparallele Computervorgänge optimiert ist. Eine Zugriffstaste ist häufig eine einzelne GPU, kann jedoch auch eine virtuelle hostseitige Entität wie ein DirectX REF-Gerät, ein WARP-Gerät (ein CPU-seitiges Gerät, das mithilfe von SSE-Anweisungen beschleunigt wird) oder die CPU selbst sein.  
  
 Sie können ein `accelerator`-Objekt erstellen, indem Sie die verfügbaren Geräte auflisten oder das Standardgerät, das Referenzgerät oder das WARP-Gerät abrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="dtor"></a></a> ~ Accelerator 

 Zerstört das `accelerator`-Objekt.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="ctor"></a>Zugriffstaste 

 Initialisiert eine neue Instanz der dem [zugriffstastenklasse](accelerator-class.md).  
  
```  
accelerator();

 
explicit accelerator(const std::wstring& _Device_path);

 
accelerator(const accelerator& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Device_path`  
 Der Pfad des physischen Geräts.  
  
 `_Other`  
 Die zu kopierende Zugriffstaste.  
  
##  <a name="cpu_accelerator"></a>cpu_accelerator 

 Ruft eine Zeichenfolge für die CPU-Zugriffstaste.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="create_view"></a>CREATE_VIEW 

 Erstellt und gibt ein `accelerator_view` Objekt auf dieser Zugriffstaste, die unter Verwendung der angegebenen Warteschlange. Wenn der queuingmodus nicht angegeben wird, wird das neue `accelerator_view` verwendet die [queuing_mode::immediate](concurrency-namespace-enums-amp.md#queuing_mode) queuingmodus.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Parameter  
 `qmode`  
 Der Warteschlangen-Modus.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein neues `accelerator_view` Objekt auf dieser Zugriffstaste, die unter Verwendung der angegebenen Warteschlange.  
  
##  <a name="dedicated_memory"></a>dedicated_memory 

 Ruft den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB ab.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="default_accelerator"></a>default_accelerator 

 Ruft eine Zeichenfolgenkonstante für die standardmäßige `accelerator` ab.  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="default_cpu_access_type"></a>default_cpu_access_type-Objekt 

 Die Standardeinstellung cpu [Access_type](concurrency-namespace-enums-amp.md#access_type)für Arrays und implizite speicherbelegungen für diese `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="default_view"></a>default_view 

 Ruft die Accelerator-Standardansicht, die zugeordnet ist die `accelerator`.  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="description"></a>Beschreibung 

 Ruft eine kurze Beschreibung des `accelerator`-Geräts ab.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="device_path"></a>device_path 

 Ruft den Pfad der Zugriffstaste. Der Pfad ist im System eindeutig.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="direct3d_ref"></a>direct3d_ref 

 Ruft eine Zeichenfolge für die Zugriffstaste eine Direct3D-Verweis.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="direct3d_warp"></a>direct3d_warp 

 Ruft die Zeichenfolge für die Konstante ein `accelerator` Objekt, das Sie zur Ausführung von C++ AMP-Code in Multi-Core-CPUs mit Streaming SIMD Extensions (SSE) verwenden können.  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="get_all"></a>get_all 

 Gibt einen Vektor von `accelerator`-Objekten zurück, die alle verfügbaren Zugriffstasten darstellen.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Vektor der verfügbaren Zugriffstasten  
  
##  <a name="get_auto_selection_view"></a>get_auto_selection_view 

 Gibt das accelerator_view-Objekt zur automatischen Auswahl zurück, das, sofern als parallel_for_each-Ziel angegeben, im accelerator_view-Ziel resultiert, damit der parallel_for_each-Kernels von der Laufzeit automatisch ausgewählt wird. Für alle anderen Zwecke ist das von dieser Methode zurückgegebene accelerator_view-Objekt, mit dem accelerator_view-Standardobjekt der Standardzugriffstaste identisch.  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das accelerator_view-Objekt zur automatischen Auswahl.  
  
##  <a name="get_dedicated_memory"></a>get_dedicated_memory 

 Gibt den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB zurück.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den dedizierten Arbeitsspeicher für die `accelerator`, in Kilobyte.  
  
##  <a name="get_default_cpu_access_type"></a>get_default_cpu_access_type 

 Ruft das standardmäßige CPU-access_type-Objekt für die Puffer zurück, die auf dieser Zugriffstaste erstellt werden.  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das standardmäßige CPU-access_type-Objekt für die Puffer, die auf dieser Zugriffstaste erstellt werden.  
  
##  <a name="get_default_view"></a>get_default_view 

 Gibt das standardmäßige `accelerator_view`-Objekt zurück, das mit dem `accelerator`-Objekt verknüpft ist.  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardeinstellung `accelerator_view` -Objekt, das zugeordnet ist die `accelerator`.  
  
##  <a name="get_description"></a>get_Description 

 Gibt eine kurze Beschreibung des `accelerator`-Geräts zurück.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine kurze Beschreibung der `accelerator` Gerät.  
  
##  <a name="get_device_path"></a>get_device_path 

 Gibt den Pfad der Zugriffstaste. Der Pfad ist im System eindeutig.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der systemweit eindeutige Instanz Gerätepfad.  
  
##  <a name="get_has_display"></a>get_has_display 

 Gibt einen booleschen Wert, der angibt, ob die `accelerator` eine Anzeige ausgeben kann.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die `accelerator` an eine Anzeige ausgeben kann; andernfalls `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Bestimmt, für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist. Andernfalls `false`.  
  
##  <a name="get_is_emulated"></a>get_is_emulated 

 Bestimmt, ob das `accelerator`-Objekt emuliert ist.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das `accelerator`-Objekt emuliert wird. Andernfalls `false`.  
  
##  <a name="get_supports_cpu_shared_memory"></a>get_supports_cpu_shared_memory 

 Gibt einen booleschen Wert zurück, der angibt, ob die Zugriffstaste Arbeitsspeicher unterstützt, auf den sowohl die Zugriffstaste als auch die CPU zugreifen können.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Zugriffstaste freigegebenen CPU-Arbeitsspeicher unterstützt; andernfalls `false`.  
  
##  <a name="get_supports_double_precision"></a>get_supports_double_precision 

 Gibt einen booleschen Wert zurück, der angibt, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt, einschließlich Fused Multiply Add (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt; andernfalls `false`.  
  
##  <a name="get_supports_limited_double_precision"></a>get_supports_limited_double_precision 

 Gibt einen booleschen Wert, der angibt, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen doppelter Genauigkeit verfügt. Verfügt die Zugriffstaste nur eingeschränkte Unterstützung, dann fused multiply hinzufügen (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double` werden nicht unterstützt.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Zugriffstaste über beschränkte Unterstützung für double Precision mathematische; verfügt andernfalls `false`.  
  
##  <a name="get_version"></a>get_version 

 Gibt die Version des `accelerator`-Objekts zurück.  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator`.  
  
##  <a name="has_display"></a>has_display 

 Ruft einen booleschen Wert, der angibt, ob die `accelerator` eine Anzeige ausgeben kann.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Ruft einen booleschen Wert, der angibt, ob die `accelerator` die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="is_emulated"></a>is_emulated 

 Ruft einen booleschen Wert, der angibt, ob die `accelerator` emuliert wird.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="operator_neq"></a>Operator! = 

 Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false`Wenn die beiden `accelerator` -Objekte identisch sind, andernfalls `true`.  
  
##  <a name="operator_eq"></a>Operator = 

 Kopiert den Inhalt des angegebenen `accelerator`-Objekts in dieses Objekt.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `accelerator`-Objekt.  
  
##  <a name="operator_eq_eq"></a>Operator == 

 Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die andere `accelerator` Objekt entspricht dies `accelerator` Objekt; andernfalls `false`.  
  
##  <a name="set_default"></a>set_default 

 Legt die Standardzugriffstaste fest, die für jeden Vorgang verwendet werden soll, der die Standardzugriffstaste implizit verwendet. Diese Methode ist nur erfolgreich, wenn die von der Laufzeit ausgewählte Standardzugriffstaste nicht bereits in einem Vorgang verwendet wurde, der die Standardzugriffstaste implizit verwendet  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Parameter  
 `_Path`  
 Der Pfad zur Zugriffstaste.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Aufruf die Einstellung der Standardzugriffstaste erfolgreich vornimmt. Andernfalls `false`.  
  
##  <a name="set_default_cpu_access_type"></a>set_default_cpu_access_type 

 Legen Sie das Standard-CPU-access_type-Objekt für die Arrays fest, die auf dieser Zugriffstaste erstellt werden oder für die Speicherbelegungen als Teil des array_views-Objekts, auf das über diese Zugriffstaste zugegriffen wurde. Diese Methode ist nur erfolgreich, wenn das default_cpu_access_type-Objekt für die Zugriffstaste nicht bereits von einem vorherigen Aufruf dieser Methode überschrieben wurde und das von der Laufzeit ausgewählte default_cpu_access_type-Objekt für diese Zugriffstaste noch nicht für das Zuordnen eines Arrays oder einer impliziten Speicherbelegung verwendet wurde, die ein array_view-Objekt unterstützt, auf das über diese Zugriffstaste zugegriffen wird.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Parameter  
 `_Default_cpu_access_type`  
 Das Standard-CPU-access_type-Objekt, das für array/array_view-Speicherbelegungen auf dieser Zugriffstaste verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob das Standard-CPU-access_type-Objekt für die Zugriffstaste erfolgreich festgelegt wurde.  
  
##  <a name="supports_cpu_shared_memory"></a>supports_cpu_shared_memory 

 Ruft einen booleschen Wert ab, der angibt, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="supports_double_precision"></a>supports_double_precision 

 Ruft einen booleschen Wert, der angibt, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="supports_limited_double_precision"></a>supports_limited_double_precision 

 Ruft einen booleschen Wert, der angibt, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen doppelter Genauigkeit verfügt. Verfügt die Zugriffstaste nur eingeschränkte Unterstützung, dann fused multiply hinzufügen (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double` werden nicht unterstützt.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="version"></a>Version 

 Ruft die Version der `accelerator` ab.  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="dtor"></a></a> ~ accelerator_view-Objekt 

 Zerstört die [Accelerator_view](accelerator-view-class.md) Objekt.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="accelerator"></a>Zugriffstaste 

 Ruft die `accelerator` -Objekt für die [Accelerator_view](accelerator-view-class.md) Objekt.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="ctor"></a>accelerator_view-Objekt 

 Initialisiert eine neue Instanz der dem [Accelerator_view](accelerator-view-class.md) -Klasse durch Kopieren einer vorhandenen `accelerator_view` Objekt.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `accelerator_view`-Objekt.  
  
##  <a name="create_marker"></a>create_marker 

 Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein future-Objekt zum Nachverfolgen des Abschlusses aller Befehle, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
##  <a name="flush"></a>leeren 

 Sendet alle ausstehenden Befehle in der Warteschlange für die [Accelerator_view](accelerator-view-class.md) Objekt zur Ausführung der Zugriffstaste.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
##  <a name="get_accelerator"></a>get_accelerator 

 Gibt die `accelerator` -Objekt für die [Accelerator_view](accelerator-view-class.md) Objekt.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `accelerator` -Objekt für die `accelerator_view` Objekt.  
  
##  <a name="get_is_auto_selection"></a>get_is_auto_selection 

 Gibt einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird ein [Parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Laufzeit eine entsprechende Zugriffstaste automatisch auswählt; andernfalls `false`.  
  
##  <a name="get_is_debug"></a>get_is_debug 

 Gibt einen booleschen Wert, der angibt, ob die [Accelerator_view](accelerator-view-class.md) -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die `accelerator_view` -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
##  <a name="get_queuing_mode"></a>get_queuing_mode 

 Gibt den queuingmodus für das [Accelerator_view](accelerator-view-class.md) Objekt.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den queuingmodus für das `accelerator_view` Objekt.  
  
##  <a name="get_version"></a>get_version 

 Gibt die Version der [Accelerator_view](accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator_view`.  
  
##  <a name="is_auto_selection"></a>is_auto_selection 

 Ruft einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird ein [Parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="is_debug"></a>is_debug 

 Ruft einen booleschen Wert, der angibt, ob die [Accelerator_view](accelerator-view-class.md) -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="operator_neq"></a>Operator! = 

 Vergleicht dieses [Accelerator_view](accelerator-view-class.md) Objekt mit einem anderen und gibt `false` werden; andernfalls `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false`, wenn die beiden Objekte identisch sind, andernfalls `true`.  
  
##  <a name="operator_eq"></a>Operator = 

 Kopiert den Inhalt des angegebenen [Accelerator_view](accelerator-view-class.md) -Objekts in dieses Objekt.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator_view`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die geänderte `accelerator_view` Objekt.  
  
##  <a name="operator_eq_eq"></a>Operator == 

 Vergleicht dieses [Accelerator_view](accelerator-view-class.md) Objekt mit einem anderen und gibt `true` werden; andernfalls `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die beiden Objekte identisch sind, andernfalls `false`.  
  
##  <a name="queuing_mode"></a>queuing_mode 

 Ruft den queuingmodus für das [Accelerator_view](accelerator-view-class.md) Objekt.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="version"></a>Version 

 Ruft die Version des der [Accelerator_view](accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="wait"></a>Warte 

 Wartet, bis alle Befehle an übermittelt die [Accelerator_view](accelerator-view-class.md) Objekt abgeschlossen.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

