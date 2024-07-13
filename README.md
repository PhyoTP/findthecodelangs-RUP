code for camera:
```cs

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class CameraScript : MonoBehaviour
{
    private GameObject model;
    void Awake()
    {
        Cursor.lockState = CursorLockMode.Locked;
        model = GameObject.Find("ftclModel");
    }

    void Update()
    {
        //mouse control
        transform.RotateAround(model.transform.position, Vector3.up, Input.GetAxis("Mouse X"));
        transform.RotateAround(model.transform.position, -transform.right, Input.GetAxis("Mouse Y"));

        if (Cursor.lockState == CursorLockMode.None && Input.GetMouseButtonDown(1))
        {
            Cursor.lockState = CursorLockMode.Locked;
        }
        else if (Cursor.lockState == CursorLockMode.Locked && Input.GetKeyDown(KeyCode.Escape))
        {
            Cursor.lockState = CursorLockMode.None;
        }

        
    }


}```
