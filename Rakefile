# usage rake go
desc "Generate website, add, commit and deploy"
task :go do
    system "git add ."
    message = "Site generated at #{Time.now.utc}"
    system "git commit -am \"#{message}\""
    system "git push"
    system "bundle exec jekyll build --incremental"
    cd "_site" do
    	message = "Site updated at #{time}"
    	system "git add ."
    	system "git commit -a -m '#{message}'"
    	system "git push live"
		puts "\n## Pushing Live @ #{time}"
	end
end