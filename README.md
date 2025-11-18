# denoising-challenges


# For large files to be uploaded to Github: split -b 20m ./cmps_for_denoising_751_71_1285.bi

Prepare the data:

	cat data/cmps_* >cmps_for_denoising_751_71_1285.bin

Visualize the results:

	from pyseistr import binread
	dt=0.004; dx=0.05; dy=0.0125; ox=-1.75; oy=686.25
	nt,nx,ny=751,71,1285
	data=binread("cmps_for_denoising_751_71_1285.bin",n1=751,n2=71,n3=1285)
	import matplotlib.pyplot as plt
	plt.imshow(data[:,30,:], clim=[-0.01,0.01], aspect='auto', extent=[oy, (ny-1)*dy+oy, (nt-1)*dt, 0 ]);
	plt.xlabel('CMP position (km)');plt.ylabel("Time (s)")
	plt.title("Challenging data to be denoised")
	plt.savefig("cmps.png")
	plt.show()


<p align="center">
<img src='https://github.com/aaspip/gallery/blob/main/denoising-challenges/cmps.png' alt='comp' width=960/>
</p>

