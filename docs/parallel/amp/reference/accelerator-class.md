---
title: "Zugriffstastenklasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstastenklasse"
ms.assetid: 37eed593-cf87-4611-9cdc-e98df6c2377a
caps.latest.revision: 29
caps.handback.revision: "29"
ms.author: "mblome"
manager: "ghogen"
---
# Zugriffstastenklasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Zugriffstaste ist eine Hardwarefunktion, die für datenparallele Computervorgänge optimiert ist. Eine Zugriffstaste ist ein Gerät, das einem PCIe-Bus angefügt wird (wie einem GPU-Computer), oder es handelt sich um einen erweiterten Befehl, der auf der Haupt-CPU festgelegt ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
class accelerator;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator:: Accelerator-Konstruktor](#accelerator__accelerator_constructor)|Initialisiert eine neue Instanz der `accelerator`-Klasse.|  
|[Accelerator:: ~ Accelerator-Destruktor](#accelerator___dtoraccelerator_destructor)|Zerstört das `accelerator`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator:: CREATE_VIEW-Methode](#accelerator__create_view_method)|Erstellt und gibt ein `accelerator_view`-Objekt auf dieser Zugriffstaste zurück.|  
|[Accelerator:: get_all-Methode](#accelerator__get_all_method)|Gibt einen Vektor von `accelerator`-Objekten zurück, die alle verfügbaren Zugriffstasten darstellen.|  
|[Accelerator:: get_auto_selection_view-Methode](#accelerator__get_auto_selection_view_method)|Gibt das `accelerator_view`-Objekt für die automatische Auswahl zurück.|  
|[Accelerator:: get_dedicated_memory-Methode](#accelerator__get_dedicated_memory_method)|Gibt den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB zurück.|  
|[Accelerator:: get_default_cpu_access_type-Methode](#accelerator__get_default_cpu_access_type_method)|Gibt den Standardwert zurück [Access_type](../Topic/concurrency%20namespace%20enums.md#access_type) für die Puffer auf dieser Zugriffstaste erstellt.|  
|[Accelerator:: get_default_view-Methode](#accelerator__get_default_view_method)|Gibt das standardmäßige `accelerator_view`-Objekt zurück, das mit dem `accelerator`-Objekt verknüpft ist.|  
|[Accelerator:: get_Description-Methode](#accelerator__get_description_method)|Gibt eine kurze Beschreibung des `accelerator`-Geräts zurück.|  
|[Accelerator:: get_device_path-Methode](#accelerator__get_device_path_method)|Gibt den Pfad des physischen Geräts zurück.|  
|[Accelerator:: get_has_display-Methode](#accelerator__get_has_display_method)|Bestimmt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[Accelerator:: get_is_debug-Methode](#accelerator__get_is_debug_method)|Bestimmt, für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[Accelerator:: get_is_emulated-Methode](#accelerator__get_is_emulated_method)|Bestimmt, ob das `accelerator`-Objekt emuliert ist.|  
|[Accelerator:: get_supports_cpu_shared_memory-Methode](#accelerator__get_supports_cpu_shared_memory_method)|Bestimmt, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt|  
|[Accelerator:: get_supports_double_precision-Methode](#accelerator__get_supports_double_precision_method)|Bestimmt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[Accelerator:: get_supports_limited_double_precision-Methode](#accelerator__get_supports_limited_double_precision_method)|Bestimmt, ob das `accelerator`-Objekt über beschränkte Unterstützung für mathematische Funktionen mit doppelter Genauigkeit verfügt.|  
|[Accelerator:: get_version-Methode](#accelerator__get_version_method)|Gibt die Version des `accelerator`-Objekts zurück.|  
|[Accelerator:: set_default-Methode](#accelerator__set_default_method)|Gibt den Pfad der Standardzugriffstaste zurück.|  
|[Accelerator:: set_default_cpu_access_type-Methode](#accelerator__set_default_cpu_access_type_method)|Legt die Standard-CPU [Access_type](../Topic/concurrency%20namespace%20enums.md#access_type) für Arrays und implizite speicherbelegungen für diese `accelerator`.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator::! =-Operator](#accelerator__operator_neq_operator)|Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.|  
|[Accelerator:: Operator =-Operator](#accelerator__operator_eq_operator)|Kopiert den Inhalt des angegebenen `accelerator`-Objekts in dieses Objekt.|  
|[Accelerator:: Operator ==-Operator](#accelerator__operator_eq_eq_operator)|Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `true` zurück, wenn sie identisch sind; gibt andernfalls `false` zurück.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Accelerator:: cpu_accelerator-Datenmember](#accelerator__cpu_accelerator_data_member)|Ruft eine Zeichenfolgenkonstante für die CPU-`accelerator` ab.|  
|[Accelerator:: dedicated_memory-Datenmember](#accelerator__dedicated_memory_data_member)|Ruft den dedizierten Arbeitsspeicher für das `accelerator`-Objekt in KB ab.|  
|[Accelerator:: default_accelerator-Datenmember](#accelerator__default_accelerator_data_member)|Ruft eine Zeichenfolgenkonstante für die standardmäßige `accelerator` ab.|  
|[Accelerator:: default_cpu_access_type-Datenmember](#accelerator__default_cpu_access_type_data_member)|Ruft ab oder legt die Standard-CPU [Access_type](../Topic/concurrency%20namespace%20enums.md#access_type) für Arrays und implizite speicherbelegungen für diese `accelerator`.|  
|[Accelerator:: default_view-Datenmember](#accelerator__default_view_data_member)|Ruft das standardmäßige `accelerator_view`-Objekt ab, das dem `accelerator`-Element zugeordnet ist.|  
|[Accelerator:: Description-Datenmember](#accelerator__description_data_member)|Ruft eine kurze Beschreibung des `accelerator`-Geräts ab.|  
|[Accelerator:: device_path-Datenmember](#accelerator__device_path_data_member)|Ruft den Pfad des physischen Geräts ab.|  
|[Accelerator:: direct3d_ref-Datenmember](#accelerator__direct3d_ref_data_member)|Ruft eine Zeichenfolgenkonstante für eine Direct3D-Verweis-`accelerator` ab.|  
|[Accelerator:: direct3d_warp-Datenmember](#accelerator__direct3d_warp_data_member)|Ruft die Zeichenfolge für die Konstante ein [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Objekt, das Sie verwenden können, für die Ausführung von C++ AMP-Codes auf Multikern-CPUs, die Streaming SIMD Extensions (SSE) verwenden.|  
|[Accelerator:: has_display-Datenmember](#accelerator__has_display_data_member)|Ruft einen booleschen Wert ab, der angibt, ob das `accelerator`-Objekt mit einer Anzeige verbunden ist.|  
|[Accelerator:: is_debug-Datenmember](#accelerator__is_debug_data_member)|Gibt an, ob für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.|  
|[Accelerator:: is_emulated-Datenmember](#accelerator__is_emulated_data_member)|Gibt an, ob das `accelerator`-Objekt emuliert ist.|  
|[Accelerator:: supports_cpu_shared_memory-Datenmember](#accelerator__supports_cpu_shared_memory_data_member)|Gibt an, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt.|  
|[Accelerator:: supports_double_precision-Datenmember](#accelerator__supports_double_precision_data_member)|Gibt an, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt.|  
|[Accelerator:: supports_limited_double_precision-Datenmember](#accelerator__supports_limited_double_precision_data_member)|Gibt an, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen mit doppelter Genauigkeit verfügt.|  
|[Accelerator:: Version-Datenmember](#accelerator__version_data_member)|Ruft die Version der `accelerator` ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `accelerator`  
  
## <a name="remarks"></a>Hinweise  
 Eine Zugriffstaste ist eine Hardwarefunktion, die für datenparallele Computervorgänge optimiert ist. Eine Zugriffstaste ist häufig eine einzelne GPU, kann jedoch auch eine virtuelle hostseitige Entität wie ein DirectX REF-Gerät, ein WARP-Gerät (ein CPU-seitiges Gerät, das mithilfe von SSE-Anweisungen beschleunigt wird) oder die CPU selbst sein.  
  
 Sie können ein `accelerator`-Objekt erstellen, indem Sie die verfügbaren Geräte auflisten oder das Standardgerät, das Referenzgerät oder das WARP-Gerät abrufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameacceleratordtoracceleratordestructora-acceleratoraccelerator-destructor"></a><a name="accelerator___dtoraccelerator_destructor"></a>  Accelerator:: ~ Accelerator-Destruktor  
 Zerstört die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Objekt.  
  
```  
~accelerator();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameacceleratoracceleratorconstructora-acceleratoraccelerator-constructor"></a><a name="accelerator__accelerator_constructor"></a>  Accelerator:: Accelerator-Konstruktor  
 Initialisiert eine neue Instanz der dem [zugriffstastenklasse](../../../parallel/amp/reference/accelerator-class.md).  
  
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
  
##  <a name="a-nameacceleratorcpuacceleratordatamembera-acceleratorcpuaccelerator-data-member"></a><a name="accelerator__cpu_accelerator_data_member"></a>  Accelerator:: cpu_accelerator-Datenmember  
 Ruft eine Zeichenfolge für die CPU-Zugriffstaste.  
  
```  
static const wchar_t cpu_accelerator[];  
```  
  
##  <a name="a-nameacceleratorcreateviewmethoda-acceleratorcreateview-method"></a><a name="accelerator__create_view_method"></a>  Accelerator:: CREATE_VIEW-Methode  
 Erstellt und gibt ein `accelerator_view` Objekt auf dieser Zugriffstaste, die unter Verwendung der angegebenen Warteschlange. Wenn der queuingmodus nicht angegeben wird, wird das neue `accelerator_view` verwendet die [queuing_mode::immediate](../Topic/concurrency%20namespace%20enums.md#queuing_mode) queuingmodus.  
  
```  
accelerator_view create_view(queuing_mode qmode = queuing_mode_automatic);
```  
  
### <a name="parameters"></a>Parameter  
 `qmode`  
 Der Warteschlangen-Modus.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein neues `accelerator_view` Objekt auf dieser Zugriffstaste, die unter Verwendung der angegebenen Warteschlange.  
  
##  <a name="a-nameacceleratordedicatedmemorydatamembera-acceleratordedicatedmemory-data-member"></a><a name="accelerator__dedicated_memory_data_member"></a>  Accelerator:: dedicated_memory-Datenmember  
 Ruft den dedizierten Arbeitsspeicher für die [Accelerator](../../../parallel/amp/reference/accelerator-class.md), in Kilobyte.  
  
```  
__declspec(property(get= get_dedicated_memory)) size_t dedicated_memory;  
```  
  
##  <a name="a-nameacceleratordefaultacceleratordatamembera-acceleratordefaultaccelerator-data-member"></a><a name="accelerator__default_accelerator_data_member"></a>  Accelerator:: default_accelerator-Datenmember  
 Ruft eine Zeichenfolge für den Standard-Konstante [Accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
static const wchar_t default_accelerator[];  
```  
  
##  <a name="a-nameacceleratordefaultcpuaccesstypedatamembera-acceleratordefaultcpuaccesstype-data-member"></a><a name="accelerator__default_cpu_access_type_data_member"></a>  Accelerator:: default_cpu_access_type-Datenmember  
 Die Standardeinstellung cpu [Access_type](../Topic/concurrency%20namespace%20enums.md#access_type) für Arrays und implizite speicherbelegungen für diese `accelerator`.  
  
```  
__declspec(property(get= get_default_cpu_access_type)) access_type default_cpu_access_type;  
```  
  
##  <a name="a-nameacceleratordefaultviewdatamembera-acceleratordefaultview-data-member"></a><a name="accelerator__default_view_data_member"></a>  Accelerator:: default_view-Datenmember  
 Ruft die Accelerator-Standardansicht, die zugeordnet ist die [Accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_default_view)) accelerator_view default_view;  
```  
  
##  <a name="a-nameacceleratordescriptiondatamembera-acceleratordescription-data-member"></a><a name="accelerator__description_data_member"></a>  Accelerator:: Description-Datenmember  
 Ruft eine kurze Beschreibung der [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Gerät.  
  
```  
__declspec(property(get= get_description)) std::wstring description;  
```  
  
##  <a name="a-nameacceleratordevicepathdatamembera-acceleratordevicepath-data-member"></a><a name="accelerator__device_path_data_member"></a>  Accelerator:: device_path-Datenmember  
 Ruft den Pfad der Zugriffstaste. Der Pfad ist im System eindeutig.  
  
```  
__declspec(property(get= get_device_path)) std::wstring device_path;  
```  
  
##  <a name="a-nameacceleratordirect3drefdatamembera-acceleratordirect3dref-data-member"></a><a name="accelerator__direct3d_ref_data_member"></a>  Accelerator:: direct3d_ref-Datenmember  
 Ruft eine Zeichenfolge für die Zugriffstaste eine Direct3D-Verweis.  
  
```  
static const wchar_t direct3d_ref[];  
```  
  
##  <a name="a-nameacceleratordirect3dwarpdatamembera-acceleratordirect3dwarp-data-member"></a><a name="accelerator__direct3d_warp_data_member"></a>  Accelerator:: direct3d_warp-Datenmember  
 Ruft die Zeichenfolge für die Konstante ein [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Objekt, das Sie zur Ausführung von C++ AMP-Code in Multi-Core-CPUs mit Streaming SIMD Extensions (SSE) verwenden können.  
  
```  
static const wchar_t direct3d_warp[];  
```  
  
##  <a name="a-nameacceleratorgetallmethoda-acceleratorgetall-method"></a><a name="accelerator__get_all_method"></a>  Accelerator:: get_all-Methode  
 Gibt einen Vektor von `accelerator`-Objekten zurück, die alle verfügbaren Zugriffstasten darstellen.  
  
```  
static inline std::vector<accelerator> get_all();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Vektor der verfügbaren Zugriffstasten  
  
##  <a name="a-nameacceleratorgetautoselectionviewmethoda-acceleratorgetautoselectionview-method"></a><a name="accelerator__get_auto_selection_view_method"></a>  Accelerator:: get_auto_selection_view-Methode  
 Gibt das accelerator_view-Objekt zur automatischen Auswahl zurück, das, sofern als parallel_for_each-Ziel angegeben, im accelerator_view-Ziel resultiert, damit der parallel_for_each-Kernels von der Laufzeit automatisch ausgewählt wird. Für alle anderen Zwecke ist das von dieser Methode zurückgegebene accelerator_view-Objekt, mit dem accelerator_view-Standardobjekt der Standardzugriffstaste identisch.  
  
```  
static accelerator_view __cdecl get_auto_selection_view();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das accelerator_view-Objekt zur automatischen Auswahl.  
  
##  <a name="a-nameacceleratorgetdedicatedmemorymethoda-acceleratorgetdedicatedmemory-method"></a><a name="accelerator__get_dedicated_memory_method"></a>  Accelerator:: get_dedicated_memory-Methode  
 Gibt den dedizierten Arbeitsspeicher für die [Accelerator](../../../parallel/amp/reference/accelerator-class.md), in Kilobyte.  
  
```  
size_t get_dedicated_memory() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den dedizierten Arbeitsspeicher für die `accelerator`, in Kilobyte.  
  
##  <a name="a-nameacceleratorgetdefaultcpuaccesstypemethoda-acceleratorgetdefaultcpuaccesstype-method"></a><a name="accelerator__get_default_cpu_access_type_method"></a>  Accelerator:: get_default_cpu_access_type-Methode  
 Ruft das standardmäßige CPU-access_type-Objekt für die Puffer zurück, die auf dieser Zugriffstaste erstellt werden.  
  
```  
access_type get_default_cpu_access_type() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das standardmäßige CPU-access_type-Objekt für die Puffer, die auf dieser Zugriffstaste erstellt werden.  
  
##  <a name="a-nameacceleratorgetdefaultviewmethoda-acceleratorgetdefaultview-method"></a><a name="accelerator__get_default_view_method"></a>  Accelerator:: get_default_view-Methode  
 Gibt die standardmäßige `accelerator_view` -Objekt, das zugeordnet ist die [Accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
accelerator_view get_default_view() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Standardeinstellung `accelerator_view` -Objekt, das zugeordnet ist die `accelerator`.  
  
##  <a name="a-nameacceleratorgetdescriptionmethoda-acceleratorgetdescription-method"></a><a name="accelerator__get_description_method"></a>  Accelerator:: get_Description-Methode  
 Gibt eine kurze Beschreibung der [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Gerät.  
  
```  
std::wstring get_description() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine kurze Beschreibung der `accelerator` Gerät.  
  
##  <a name="a-nameacceleratorgetdevicepathmethoda-acceleratorgetdevicepath-method"></a><a name="accelerator__get_device_path_method"></a>  Accelerator:: get_device_path-Methode  
 Gibt den Pfad der Zugriffstaste. Der Pfad ist im System eindeutig.  
  
```  
std::wstring get_device_path() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der systemweit eindeutige Instanz Gerätepfad.  
  
##  <a name="a-nameacceleratorgethasdisplaymethoda-acceleratorgethasdisplay-method"></a><a name="accelerator__get_has_display_method"></a>  Accelerator:: get_has_display-Methode  
 Gibt einen booleschen Wert, der angibt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) an eine Anzeige ausgeben kann.  
  
```  
bool get_has_display() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die `accelerator` an eine Anzeige ausgeben kann; andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetisdebugmethoda-acceleratorgetisdebug-method"></a><a name="accelerator__get_is_debug_method"></a>  Accelerator:: get_is_debug-Methode  
 Bestimmt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn für das `accelerator`-Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist. Andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetisemulatedmethoda-acceleratorgetisemulated-method"></a><a name="accelerator__get_is_emulated_method"></a>  Accelerator:: get_is_emulated-Methode  
 Bestimmt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) emuliert wird.  
  
```  
bool get_is_emulated() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das `accelerator`-Objekt emuliert wird. Andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetsupportscpusharedmemorymethoda-acceleratorgetsupportscpusharedmemory-method"></a><a name="accelerator__get_supports_cpu_shared_memory_method"></a>  Accelerator:: get_supports_cpu_shared_memory-Methode  
 Gibt einen booleschen Wert zurück, der angibt, ob die Zugriffstaste Arbeitsspeicher unterstützt, auf den sowohl die Zugriffstaste als auch die CPU zugreifen können.  
  
```  
bool get_supports_cpu_shared_memory() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Zugriffstaste freigegebenen CPU-Arbeitsspeicher unterstützt; andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetsupportsdoubleprecisionmethoda-acceleratorgetsupportsdoubleprecision-method"></a><a name="accelerator__get_supports_double_precision_method"></a>  Accelerator:: get_supports_double_precision-Methode  
 Gibt einen booleschen Wert zurück, der angibt, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt, einschließlich Fused Multiply Add (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double`.  
  
```  
bool get_supports_double_precision() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt; andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetsupportslimiteddoubleprecisionmethoda-acceleratorgetsupportslimiteddoubleprecision-method"></a><a name="accelerator__get_supports_limited_double_precision_method"></a>  Accelerator:: get_supports_limited_double_precision-Methode  
 Gibt einen booleschen Wert, der angibt, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen doppelter Genauigkeit verfügt. Verfügt die Zugriffstaste nur eingeschränkte Unterstützung, dann fused multiply hinzufügen (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double` werden nicht unterstützt.  
  
```  
bool get_supports_limited_double_precision() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Zugriffstaste über beschränkte Unterstützung für double Precision mathematische; verfügt andernfalls `false`.  
  
##  <a name="a-nameacceleratorgetversionmethoda-acceleratorgetversion-method"></a><a name="accelerator__get_version_method"></a>  Accelerator:: get_version-Methode  
 Gibt die Version der [Accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator`.  
  
##  <a name="a-nameacceleratorhasdisplaydatamembera-acceleratorhasdisplay-data-member"></a><a name="accelerator__has_display_data_member"></a>  Accelerator:: has_display-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) an eine Anzeige ausgeben kann.  
  
```  
__declspec(property(get= get_has_display)) bool has_display;  
```  
  
##  <a name="a-nameacceleratorisdebugdatamembera-acceleratorisdebug-data-member"></a><a name="accelerator__is_debug_data_member"></a>  Accelerator:: is_debug-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorisemulateddatamembera-acceleratorisemulated-data-member"></a><a name="accelerator__is_emulated_data_member"></a>  Accelerator:: is_emulated-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) emuliert wird.  
  
```  
__declspec(property(get= get_is_emulated)) bool is_emulated;  
```  
  
##  <a name="a-nameacceleratoroperatorneqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_neq_operator"></a>  Accelerator::! =-Operator  
 Vergleicht dieses `accelerator`-Objekt mit einem anderen und gibt `false` zurück, wenn sie identisch sind; gibt andernfalls `true` zurück.  
  
```  
bool operator!= (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false` Wenn die beiden `accelerator` -Objekte identisch sind, andernfalls `true`.  
  
##  <a name="a-nameacceleratoroperatoreqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_operator"></a>  Accelerator:: Operator =-Operator  
 Kopiert den Inhalt des angegebenen [Accelerator](../../../parallel/amp/reference/accelerator-class.md) -Objekts diesem Objekt zu.  
  
```  
accelerator& operator= (const accelerator& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `accelerator`-Objekt.  
  
##  <a name="a-nameacceleratoroperatoreqeqoperatora-acceleratoroperator-operator"></a><a name="accelerator__operator_eq_eq_operator"></a>  Accelerator:: Operator ==-Operator  
 Vergleicht dieses [Accelerator](../../../parallel/amp/reference/accelerator-class.md) Objekt mit einem anderen und gibt `true` werden; andernfalls `false`.  
  
```  
bool operator== (const accelerator& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die andere `accelerator` Objekt entspricht dies `accelerator` Objekt; andernfalls `false`.  
  
##  <a name="a-nameacceleratorsetdefaultmethoda-acceleratorsetdefault-method"></a><a name="accelerator__set_default_method"></a>  Accelerator:: set_default-Methode  
 Legt die Standardzugriffstaste fest, die für jeden Vorgang verwendet werden soll, der die Standardzugriffstaste implizit verwendet. Diese Methode ist nur erfolgreich, wenn die von der Laufzeit ausgewählte Standardzugriffstaste nicht bereits in einem Vorgang verwendet wurde, der die Standardzugriffstaste implizit verwendet  
  
```  
static inline bool set_default(std::wstring _Path);
```  
  
### <a name="parameters"></a>Parameter  
 `_Path`  
 Der Pfad zur Zugriffstaste.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn der Aufruf die Einstellung der Standardzugriffstaste erfolgreich vornimmt. Andernfalls `false`.  
  
##  <a name="a-nameacceleratorsetdefaultcpuaccesstypemethoda-acceleratorsetdefaultcpuaccesstype-method"></a><a name="accelerator__set_default_cpu_access_type_method"></a>  Accelerator:: set_default_cpu_access_type-Methode  
 Legen Sie das Standard-CPU-access_type-Objekt für die Arrays fest, die auf dieser Zugriffstaste erstellt werden oder für die Speicherbelegungen als Teil des array_views-Objekts, auf das über diese Zugriffstaste zugegriffen wurde. Diese Methode ist nur erfolgreich, wenn das default_cpu_access_type-Objekt für die Zugriffstaste nicht bereits von einem vorherigen Aufruf dieser Methode überschrieben wurde und das von der Laufzeit ausgewählte default_cpu_access_type-Objekt für diese Zugriffstaste noch nicht für das Zuordnen eines Arrays oder einer impliziten Speicherbelegung verwendet wurde, die ein array_view-Objekt unterstützt, auf das über diese Zugriffstaste zugegriffen wird.  
  
```  
bool set_default_cpu_access_type(access_type _Default_cpu_access_type);
```  
  
### <a name="parameters"></a>Parameter  
 `_Default_cpu_access_type`  
 Das Standard-CPU-access_type-Objekt, das für array/array_view-Speicherbelegungen auf dieser Zugriffstaste verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob das Standard-CPU-access_type-Objekt für die Zugriffstaste erfolgreich festgelegt wurde.  
  
##  <a name="a-nameacceleratorsupportscpusharedmemorydatamembera-acceleratorsupportscpusharedmemory-data-member"></a><a name="accelerator__supports_cpu_shared_memory_data_member"></a>  Accelerator:: supports_cpu_shared_memory-Datenmember  
 Ruft einen booleschen Wert ab, der angibt, ob das `accelerator`-Objekt freigegebenen Arbeitsspeicher unterstützt.  
  
```  
__declspec(property(get= get_supports_cpu_shared_memory)) bool supports_cpu_shared_memory;  
```  
  
##  <a name="a-nameacceleratorsupportsdoubleprecisiondatamembera-acceleratorsupportsdoubleprecision-data-member"></a><a name="accelerator__supports_double_precision_data_member"></a>  Accelerator:: supports_double_precision-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die Zugriffstaste mathematische Funktionen mit doppelter Genauigkeit unterstützt.  
  
```  
__declspec(property(get= get_supports_double_precision)) bool supports_double_precision;  
```  
  
##  <a name="a-nameacceleratorsupportslimiteddoubleprecisiondatamembera-acceleratorsupportslimiteddoubleprecision-data-member"></a><a name="accelerator__supports_limited_double_precision_data_member"></a>  Accelerator:: supports_limited_double_precision-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die Zugriffstaste über beschränkte Unterstützung für mathematische Funktionen doppelter Genauigkeit verfügt. Verfügt die Zugriffstaste nur eingeschränkte Unterstützung, dann fused multiply hinzufügen (FMA), Division, Kehrwert und Umwandlung zwischen `int` und `double` werden nicht unterstützt.  
  
```  
__declspec(property(get= get_supports_limited_double_precision)) bool supports_limited_double_precision;  
```  
  
##  <a name="a-nameacceleratorversiondatamembera-acceleratorversion-data-member"></a><a name="accelerator__version_data_member"></a>  Accelerator:: Version-Datenmember  
 Ruft die Version des der [Accelerator](../../../parallel/amp/reference/accelerator-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewdtoracceleratorviewdestructora-acceleratorviewacceleratorview-destructor"></a><a name="accelerator_view___dtoraccelerator_view_destructor"></a>  Accelerator_view:: ~ Accelerator_view-Destruktor  
 Zerstört die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt.  
  
```  
~accelerator_view();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
##  <a name="a-nameacceleratorviewacceleratordatamembera-acceleratorviewaccelerator-data-member"></a><a name="accelerator_view__accelerator_data_member"></a>  accelerator_view:: Accelerator-Datenmember  
 Ruft die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) -Objekt für die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt.  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
##  <a name="a-nameacceleratorviewacceleratorviewconstructora-acceleratorviewacceleratorview-constructor"></a><a name="accelerator_view__accelerator_view_constructor"></a>  accelerator_view:: accelerator_view-Konstruktor  
 Initialisiert eine neue Instanz der dem [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Klasse durch Kopieren einer vorhandenen `accelerator_view` Objekt.  
  
```  
accelerator_view(const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das zu kopierende `accelerator_view`-Objekt.  
  
##  <a name="a-nameacceleratorviewcreatemarkermethoda-acceleratorviewcreatemarker-method"></a><a name="accelerator_view__create_marker_method"></a>  accelerator_view:: create_marker-Methode  
 Gibt ein future-Objekt zurück, um den Abschluss aller Befehle nachzuverfolgen, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
```  
concurrency::completion_future create_marker();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein future-Objekt zum Nachverfolgen des Abschlusses aller Befehle, die bis jetzt zu diesem `accelerator_view`-Objekt gesendet wurden.  
  
##  <a name="a-nameacceleratorviewflushmethoda-acceleratorviewflush-method"></a><a name="accelerator_view__flush_method"></a>  accelerator_view:: Flush-Methode  
 Sendet alle ausstehenden Befehle in der Warteschlange für die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt zur Ausführung der Zugriffstaste.  
  
```  
void flush();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
##  <a name="a-nameacceleratorviewgetacceleratormethoda-acceleratorviewgetaccelerator-method"></a><a name="accelerator_view__get_accelerator_method"></a>  accelerator_view:: get_accelerator-Methode  
 Gibt die [Accelerator](../../../parallel/amp/reference/accelerator-class.md) -Objekt für die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt.  
  
```  
accelerator get_accelerator() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das `accelerator` -Objekt für die `accelerator_view` Objekt.  
  
##  <a name="a-nameacceleratorviewgetisautoselectionmethoda-acceleratorviewgetisautoselection-method"></a><a name="accelerator_view__get_is_auto_selection_method"></a>  accelerator_view:: get_is_auto_selection-Methode  
 Gibt einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird eine [Parallel_for_each](../Topic/concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
bool get_is_auto_selection() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Laufzeit eine entsprechende Zugriffstaste automatisch auswählt; andernfalls `false`.  
  
##  <a name="a-nameacceleratorviewgetisdebugmethoda-acceleratorviewgetisdebug-method"></a><a name="accelerator_view__get_is_debug_method"></a>  accelerator_view:: get_is_debug-Methode  
 Gibt einen booleschen Wert, der angibt, ob die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
bool get_is_debug() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der angibt, ob die `accelerator_view` -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
##  <a name="a-nameacceleratorviewgetqueuingmodemethoda-acceleratorviewgetqueuingmode-method"></a><a name="accelerator_view__get_queuing_mode_method"></a>  accelerator_view:: get_queuing_mode-Methode  
 Gibt den queuingmodus für das [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt.  
  
```  
queuing_mode get_queuing_mode() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den queuingmodus für das `accelerator_view` Objekt.  
  
##  <a name="a-nameacceleratorviewgetversionmethoda-acceleratorviewgetversion-method"></a><a name="accelerator_view__get_version_method"></a>  accelerator_view:: get_version-Methode  
 Gibt die Version der [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).  
  
```  
unsigned int get_version() const;

 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version der `accelerator_view`.  
  
##  <a name="a-nameacceleratorviewisautoselectiondatamembera-acceleratorviewisautoselection-data-member"></a><a name="accelerator_view__is_auto_selection_data_member"></a>  accelerator_view:: is_auto_selection-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die Laufzeit automatisch eine entsprechende Zugriffstaste auswählt, wenn das accelerator_view-Objekt übergeben wird eine [Parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each).  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
##  <a name="a-nameacceleratorviewisdebugdatamembera-acceleratorviewisdebug-data-member"></a><a name="accelerator_view__is_debug_data_member"></a>  accelerator_view:: is_debug-Datenmember  
 Ruft einen booleschen Wert, der angibt, ob die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekt die DEBUG-Ebene für eine umfangreiche Fehlerberichterstattung aktiviert ist.  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
##  <a name="a-nameacceleratorviewoperatorneqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_neq_operator"></a>  accelerator_view::! =-Operator  
 Vergleicht dieses [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt mit einem anderen und gibt `false` werden; andernfalls `true`.  
  
```  
bool operator!= (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `false`, wenn die beiden Objekte identisch sind, andernfalls `true`.  
  
##  <a name="a-nameacceleratorviewoperatoreqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_operator"></a>  accelerator_view:: Operator =-Operator  
 Kopiert den Inhalt des angegebenen [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) -Objekts in dieses Objekt.  
  
```  
accelerator_view& operator= (const accelerator_view& _Other);
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Das `accelerator_view`-Objekt, aus dem kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die geänderte `accelerator_view` Objekt.  
  
##  <a name="a-nameacceleratorviewoperatoreqeqoperatora-acceleratorviewoperator-operator"></a><a name="accelerator_view__operator_eq_eq_operator"></a>  accelerator_view:: Operator ==-Operator  
 Vergleicht dieses [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt mit einem anderen und gibt `true` werden; andernfalls `false`.  
  
```  
bool operator== (const accelerator_view& _Other) const;

 
```  
  
### <a name="parameters"></a>Parameter  
 `_Other`  
 Die `accelerator_view` dieses Objekt zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die beiden Objekte identisch sind, andernfalls `false`.  
  
##  <a name="a-nameacceleratorviewqueuingmodedatamembera-acceleratorviewqueuingmode-data-member"></a><a name="accelerator_view__queuing_mode_data_member"></a>  accelerator_view:: queuing_mode-Datenmember  
 Ruft den queuingmodus für das [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt.  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
##  <a name="a-nameacceleratorviewversiondatamembera-acceleratorviewversion-data-member"></a><a name="accelerator_view__version_data_member"></a>  accelerator_view:: Version-Datenmember  
 Ruft die Version des der [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md).  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
##  <a name="a-nameacceleratorviewwaitmethoda-acceleratorviewwait-method"></a><a name="accelerator_view__wait_method"></a>  accelerator_view:: Wait-Methode  
 Wartet, bis alle Befehle an übermittelt die [Accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) Objekt abgeschlossen.  
  
```  
void wait();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `void`zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace (C++-AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
