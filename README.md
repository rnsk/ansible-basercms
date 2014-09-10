ansible-basercms
================

### Apache + MySQL + PHP + baserCMS + Composer

- Requires Ansible 1.7 or newer
- Expects CentOS/RHEL 6.x hosts

baserCMS の動作環境を構築するシンプルな Playbook です。  
CentOS6.x 上での構築を想定しています。  
`hosts.example` を `hosts` にリネームして、実際のIPアドレスもしくはホスト名を入力して使用してください。

These playbooks deploy a all-in-one configuration of the baserCMS.  
To use, copy the `hosts.example` file to `hosts` and 
edit the `hosts` inventory file to include the names or URLs of the servers
you want to deploy.

Then run the playbook, like this:

    ansible-playbook -i hosts playbook.yml

#### MySQL
- database name: basercms
- database username: basercms
- database password: basercms

#### Apache
- document root: '/var/www/basercms'
- user: 'basercms'
- group: 'basercms'

これらの設定は『group_vars/all』に記述しています。  
設定を変更する場合はこのファイルを修正するか、上位設定ファイルを作成してください。

ansible では設定の優先度は以下のようになっています。

    host_vars > group_vars(Group Name) > group_vars(all)
