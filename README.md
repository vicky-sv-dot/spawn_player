# spawn_player
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class GameMang1 : MonoBehaviour
{
    [SerializeField] private GameObject PlayerPrefab;
    [SerializeField] private GameObject Canvas;
    [SerializeField] private GameObject Camera;

    private void Awake()
    {
        Canvas.SetActive(true);
    }

    public void SpawnPlayer()
    {
        float randomValue =Random.Range(2f,7f);
        PhotonNetwork.Instantiate(PlayerPrefab.name, new Vector3(transform.position.x * randomValue, 
            0, transform.position.y * randomValue),Quaternion.identity,0);

        Canvas.SetActive(false);
        Camera.SetActive(false);
    }
}
