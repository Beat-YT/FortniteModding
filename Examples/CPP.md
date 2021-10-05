## Example c++ classes.

FortInventory
```
// Fill out your copyright notice in the Description page of Project Settings.


#pragma once

#include "CoreMinimal.h"
#include "FortPickup.h"
#include "GameFramework/Actor.h"
#include "FortInventory.generated.h"

USTRUCT(Blueprintable)
struct FFortItemList : public FFastArraySerializer
{
	GENERATED_BODY()

		UPROPERTY(EditAnywhere, BlueprintReadWrite)
	TArray<struct FFortItemEntry>                      ReplicatedEntries;                                        // 0x00B0(0x0010) (ZeroConstructor, SaveGame)
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	TArray<class UFortWorldItem*>                      ItemInstances;                                            // 0x0110(0x0010) (ZeroConstructor)
};

UCLASS()
class FORTNITEGAME_API AFortInventory : public AActor
{

	UFUNCTION(BlueprintCallable)
	void HandleInventoryLocalUpdate();

	GENERATED_BODY()
	
public:	

	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	struct FFortItemList                               Inventory;

	// Sets default values for this actor's properties
	AFortInventory();

protected:
	// Called when the game starts or when spawned
	virtual void BeginPlay() override;

public:	
	// Called every frame
	virtual void Tick(float DeltaTime) override;

	
	
};

```

FortItemDefinition
```
// Fill out your copyright notice in the Description page of Project Settings.

#pragma once

#include "CoreMinimal.h"
#include "FortPickup.h"
#include "Engine/DataAsset.h"
#include "FortItemDefinition.generated.h"

UENUM(BlueprintType)
// Enum FortniteGame.EFortRarity
enum class EFortRarity : uint8 {
	Handmade,
	Ordinary,
	Sturdy,
	Quality,
	Fine,
	Elegant,
	Masterwork,
	Epic,
	Badass,
	Legendary,
	NumRarityValues,
	EFortRarity_MAX,

};
/**
 * 
 */
UCLASS()
class FORTNITEGAME_API UFortItemDefinition : public UPrimaryDataAsset
{
	UFUNCTION(BlueprintCallable)
		class UFortItem* CreateTemporaryItemInstanceBP(int Count, int Level);

	GENERATED_BODY()

public:

	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	FText DisplayName;
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	FText Description;
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	UTexture2D* SmallPreviewImage;
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	TSoftObjectPtr<class UTexture2D> LargePreviewImage;
	UPROPERTY(EditAnywhere, BlueprintReadWrite)
	EFortRarity Rarity;
	
};
```
