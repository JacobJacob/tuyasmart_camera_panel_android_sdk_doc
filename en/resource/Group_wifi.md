### Wifi Group

#### Group List Acquisition

```java
/**
* Obtain the device list of product
* @param homeId home id
* @param groupId the group is not created, parameter groupId must be an integer -1
* @param productId the pid of the device what is using to create group
*/
TuyaHomeSdk.newHomeInstance(homeId).queryDeviceListToAddGroup(mGroupId, mProductId, new ITuyaResultCallback<List<GroupDeviceBean>>() {
            @Override
            public void onSuccess(List<GroupDeviceBean> arrayList) {
                
            }

            @Override
            public void onError(String errorCode, String errorMsg) {
                
            }
        });
```

#### Creating a Group

```java
/**
* create a group
* @param homeId home id
* @param productId the pid of the device what is using to create group
* @param name a name of the group to be created
* @param selectedDeviceIds the deviceList choosed
*/
TuyaHomeSdk.newHomeInstance(homeId).createGroup(productId, name, selectedDeviceIds, new ITuyaResultCallback<Long>() {
    @Override
    public void onSuccess(Long groupId) {
        //return groupid
    }

    @Override
    public void onError(String errorCode, String errorMsg) {
        
    }
});
```

#### Update and Save Group

```java
/**
* update and save the group
* @param groupId group id
* @param deviceIds the choosed ids
*/
TuyaHomeSdk.newGroupInstance(groupId).updateDeviceList(deviceIds, new IResultCallback() {
                @Override
                public void onError(String s, String s1) {

                }

                @Override
                public void onSuccess() {

                }
            });
```