pipeline
{
   agent{

           label
		{		
		  label'built-in'
		   customWorkspace('/mnt/data')
		}	
        }

   stages
	{

		stage('docker container creation')
		{
		  steps
		    {
			sh 'sudo docker run --name server1 -itdp 80:80 httpd'
			sh 'sudo docker run --name server2 -itdp 90:80 httpd'
			sh 'sudo docker run --name server3 -itdp 8090:80 httpd'
		    }
		
		}
		
		stage('copy index file1 inti server1')
		{

		  steps
		   {

		     dir('/data/22q1')
			{
			   sh'sudo cd /data/22q1'
			   sh'sudo docker cp index.html server1:/usr/local/apache2/htdocs'
			  

			}

			

		   }		

		}
		stage('copy index file2 into server2')
		{

		  steps
		    {
			dir('/data/22q2')
			{
			  sh 'sudo cd /data/22q2'
			  sh 'sudo docker cp index.html  server2:/usr/local/apache2/htdocs'

			}
		     }


		} 

		stage('copy index file3 in server3')

		{

		steps{

		  dir('/data/22q3')

		   {
			sh'sudo cd /data/22q3'
			sh'sudo docker cp index.html server3:/usr/local/apache2/htdocs'
			

		   }
		     }


		}


	}


}
