# GCP

## Notes

*   [See Compute Engine Startup Script Output: ](https://cloud.google.com/compute/docs/instances/startup-scripts/linux#viewing-output)

    ```
    sudo journalctl -u google-startup-scripts.service
    ```
* Keep application running in background even when disconnected: `nohup CMD &`

