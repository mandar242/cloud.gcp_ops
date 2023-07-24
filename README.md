# cloud.gcp_ops roles/playbooks to demo Ansible on GCP

This repository hosts the `cloud.gcp_ops` Ansible Collection.

The collection includes a variety of Ansible roles and playbooks to help automate the management of resources on GCP.

<!--start requires_ansible-->
## Ansible version compatibility

This collection has been tested against following Ansible versions: **>=2.12.0**.

## Included content

Click on the name of a role to view that content's documentation:

<!--start collection content-->
### Roles
Name | Description
--- | ---

### Playbooks
Name | Description
--- | ---
<!--end collection content-->
[cloud.gcp_ops.manage_http_cloud_function](https://github.com/redhat-cop/cloud.gcp_ops/roles/manage_http_cloud_function)|A role to manage http cloud functions in GCP.


## Installation and Usage

### Requirements

The [google.cloud](https://github.com/ansible-collections/google.cloud) collection MUST be installed in order for this collection to work.


### Installation
Clone the collection repository.

```shell
  mkdir -p ~/.ansible/collections/ansible_collections/cloud/gcp_ops
  cd ~/.ansible/collections/ansible_collections/cloud/gcp_ops
  git clone https://github.com/redhat-cop/cloud.gcp_ops .
```

### Using this collection

Once installed, you can reference the cloud.gcp_ops collection content by its fully qualified collection name (FQCN), for example:

```yaml
  - hosts: all
    vars:
        project: "{{ gcp_project }}"
        auth_kind: "{{ gcp_cred_kind }}"
        service_account_file: "{{ gcp_cred_file }}"
    tasks:
      - name: Create a new custom machine image
        ansible.builtin.include_role:
            name: cloud.gcp_ops.manage_machine_image
        vars:
            manage_machine_image_operation: create
            manage_machine_image_source_disk_name: "{{ disk_name }}"
            manage_machine_image_image_name: "{{ image_name }}"
            manage_machine_image_image_description: "{{ description }}"
```

### See Also

* [Ansible Using collections](https://docs.ansible.com/ansible/latest/user_guide/collections_using.html) for more details.


## Contributing to this collection

We welcome community contributions to this collection. If you find problems, please open an issue or create a PR against this collection repository.

### Testing and Development

The project uses `ansible-lint` and `black`.
Assuming this repository is checked out in the proper structure,
e.g. `collections_root/ansible_collections/cloud/gcp_ops/`, run:

```shell
  tox -e linters
```

Sanity and unit tests are run as normal:

```shell
  ansible-test sanity
```

This collection is tested using GitHub Actions. To know more about CI, refer to [CI.md](https://github.com/https://github.com/redhat-cop/cloud.gcp_ops/blob/main/CI.md).

## License

GNU General Public License v3.0 or later

See [LICENSE](https://github.com/ansible-collections/cloud.gcp_ops/blob/main/LICENSE) to see the full text.
