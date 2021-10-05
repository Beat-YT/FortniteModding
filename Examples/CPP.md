## Example c++ stuff.

Enumerations:

- Put them inside of FortniteGame.h, under the include.

[image](https://user-images.githubusercontent.com/72986221/136032472-7cd9e8bb-2dc6-4f82-b94d-eccafca45563.png)

- Whenever you want to use the enums in any c++ class, you just include "FortniteGame.h".

```
UENUM(Blueprintable)
// Enum FortniteGame.EFortCustomBodyType
enum class EFortCustomBodyType : uint8
{
	Small = 0,
	Medium = 1,
	MediumAndSmall = 2,
	Large = 3,
	LargeAndSmall = 4,
	LargeAndMedium = 5,
	All = 6,
	Deprecated = 7
};

UENUM(Blueprintable)
// Enum FortniteGame.EFortCustomGender
enum class EFortCustomGender : uint8
{
	Invalid = 0,
	Male = 1,
	Female = 2,
	Both = 3
};

UENUM(BlueprintType)
// Enum FortniteGame.EBuildingAnim
enum class EBuildingAnim : uint8
{
	EBA_None = 0,
	EBA_Building = 1,
	EBA_Breaking = 2,
	EBA_Destruction = 3,
	EBA_Placement = 4,
	EBA_DynamicLOD = 5,
	EBA_DynamicShrink = 6,
	EBA_MAX = 7
};
UENUM(BlueprintType)
// Enum FortniteGame.EFortResourceType
enum class EFortResourceType : uint8
{
	Wood = 0,
	Stone = 1,
	Metal = 2,
	Permanite = 3,
	None = 4,
	EFortResourceType_MAX = 5
};
```
